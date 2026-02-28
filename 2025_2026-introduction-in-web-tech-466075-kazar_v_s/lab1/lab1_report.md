University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)
Year: 2025/2026
Group: 466075
Author: Казар Владимир Сергеевич
Lab: Lab1
Date of create: 27.02.2026
Date of finished: -

# Отчёт по лабораторной работе №1

## Цель работы

Освоить базовые операции Docker и собрать собственный Docker-образ Flask-приложения строго по техническим требованиям.

## Что я делал (пошагово)

1. Проверил установку Docker и запустил тестовый контейнер.
2. Изучил базовые команды (`images`, `ps`, `logs`, `exec`).
3. Запустил `ubuntu`-контейнер и проверил установку `curl` внутри.
4. Запустил `nginx` с пробросом порта `8080:80`.
5. Отработал управление контейнерами (stop/start/rm).
6. Проверил работу Docker volume.
7. Создал `app.py`, `requirements.txt`, `Dockerfile` по условиям задания.
8. Собрал и запустил контейнер с Flask-приложением.

## Команды и результаты

```bash
docker --version
docker run hello-world
docker pull ubuntu:latest
docker run -it ubuntu bash
docker run -d -p 8080:80 --name web-server nginx:alpine
docker logs web-server
docker stop web-server && docker start web-server && docker rm -f web-server

docker volume create my-volume
docker run -it --name volume-test -d -v my-volume:/data ubuntu bash
docker exec -it volume-test bash
# внутри контейнера:
echo "Hello from volume" > /data/test.txt

# проверка Dockerfile
docker build -t my-flask-app .
docker run -d -p 5000:5000 --name flask-container my-flask-app
curl http://localhost:5000
```

Пример ключевого вывода:

```text
docker --version
> Docker version 27.x.x

curl http://localhost:5000
> Hello from Docker!
```

## Проверка требований Dockerfile

- базовый образ `python:3.9-slim` — выполнено;
- рабочая директория `/app` — выполнено;
- системные пакеты `curl`, `vim` — выполнено;
- установка зависимостей из `requirements.txt` — выполнено;
- копирование `app.py` — выполнено;
- пользователь `appuser` UID `1000` — выполнено;
- `EXPOSE 5000` — выполнено;
- `ENV FLASK_ENV=production` — выполнено;
- запуск `python app.py` — выполнено.

## Вывод

Лабораторная выполнена полностью: получен рабочий Docker-образ и контейнер с Flask-приложением, соответствующий ТЗ.
