University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)
Year: 2025/2026
Group: 466075
Author: Казар Владимир Сергеевич
Lab: Lab3
Date of create: 27.02.2026
Date of finished: -

# Отчёт по лабораторной работе №3

## Цель работы

Развернуть локальную систему мониторинга с Prometheus и Grafana и подключить сбор системных метрик через Node Exporter.

## Что я делал (пошагово)

1. Создал конфиг Prometheus: `prometheus/prometheus.yml`.
2. Создал Docker-сеть `monitoring`.
3. Запустил `node-exporter` для сбора метрик хоста.
4. Запустил `prometheus` с конфигом и volume для хранения данных.
5. Запустил `grafana` с volume и admin-паролем.
6. Подключил источник данных Prometheus в Grafana (`http://prometheus:9090`).
7. Подготовил базовый дашборд по метрикам CPU/памяти/диска.

## Команды и результаты

```bash
docker network create monitoring
docker volume create prometheus-data
docker volume create grafana-data

docker run -d --name node-exporter --network monitoring -p 9100:9100 \
  -v "/proc:/host/proc:ro" -v "/sys:/host/sys:ro" -v "/:/rootfs:ro" \
  prom/node-exporter --path.procfs=/host/proc --path.rootfs=/rootfs --path.sysfs=/host/sys \
  --collector.filesystem.mount-points-exclude="^/(sys|proc|dev|host|etc)($$|/)"

cd prometheus

docker run -d --name prometheus --network monitoring -p 9090:9090 \
  -v prometheus-data:/prometheus -v $(pwd):/etc/prometheus \
  prom/prometheus --config.file=/etc/prometheus/prometheus.yml --storage.tsdb.path=/prometheus \
  --storage.tsdb.retention.time=200h --web.enable-lifecycle

docker run -d --name grafana --network monitoring -p 3000:3000 \
  -v grafana-data:/var/lib/grafana -e "GF_SECURITY_ADMIN_PASSWORD=admin" grafana/grafana

curl http://localhost:9100/metrics
docker ps
```

Пример проверочного вывода:

```text
curl http://localhost:9100/metrics
> # HELP go_gc_duration_seconds A summary of the pause duration of garbage collection cycles.

docker ps
> node-exporter   Up ...   0.0.0.0:9100->9100/tcp
> prometheus      Up ...   0.0.0.0:9090->9090/tcp
> grafana         Up ...   0.0.0.0:3000->3000/tcp
```

## Вывод

Подготовлена полноценная локальная инфраструктура мониторинга. Метрики собираются через Node Exporter, Prometheus хранит и отдаёт их, Grafana визуализирует на дашбордах.
