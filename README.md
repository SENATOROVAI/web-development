# web-development

Репозиторий по дисциплине «Введение в веб технологии» (Казар Владимир Сергеевич, группа 466075, учебный год 2025).

## Технологии

- Python
- MkDocs
- Material for MkDocs
- Markdown
- Docker
- GitHub Actions
- Prometheus
- Grafana

## Структура проекта

### 1) Персональный сайт

- `my-personal-site/docs/` — страницы сайта
- `my-personal-site/docs/images/` — изображения и логотип
- `my-personal-site/mkdocs.yml` — конфигурация сайта
- `my-personal-site/my_personal_site_report.md` — отчёт по проекту сайта

### 2) Лабораторные работы

- `2025_2026-introduction-in-web-tech-466075-kazar_v_s/` — пакет лабораторных по оформлению
- `2025_2026-introduction-in-web-tech-466075-kazar_v_s/lab0/` — Lab0 + отчёт
- `2025_2026-introduction-in-web-tech-466075-kazar_v_s/lab1/` — Flask + Dockerfile + отчёт
- `2025_2026-introduction-in-web-tech-466075-kazar_v_s/lab2/` — CI/CD workflow + отчёт
- `2025_2026-introduction-in-web-tech-466075-kazar_v_s/lab3/` — Prometheus/Grafana конфигурация + отчёт
- Отдельный репозиторий для требования Lab0: [devops-lab-kazar](https://github.com/SENATOROVAI/devops-lab-kazar)

## Запуск сайта локально

```bash
cd <папка_репозитория>/my-personal-site
python -m pip install mkdocs mkdocs-material
python -m mkdocs serve
```

Сайт будет доступен по адресу `http://127.0.0.1:8000/`.

## Сборка

```bash
cd <папка_репозитория>/my-personal-site
python -m mkdocs build
```

Собранные статические файлы появляются в папке `my-personal-site/site/`.

## Что выполнено

1. Создан и оформлен персональный сайт на MkDocs с Material.
2. Добавлен отдельный отчёт по сайту с шапкой и итогами работы.
3. Подготовлен отдельный каталог лабораторных по ТЗ и оформлению.
4. Для каждой лабораторной (`lab0`, `lab1`, `lab2`, `lab3`) подготовлены:
   - файлы выполнения по заданию;
   - детальный отчёт в формате Markdown с шапкой, пошаговым выполнением, командами и результатами.
