# 2025_2026-introduction-in-web-tech-k66666-filianin_i_v

Персональный сайт, выполненный в рамках курсовой работы по дисциплине «Введение в веб-технологии».

## Технологии

- Python
- MkDocs
- Material for MkDocs
- Markdown

## Структура проекта

- `docs/` — страницы сайта
- `docs/images/` — изображения и логотип
- `mkdocs.yml` — конфигурация сайта

## Локальный запуск

```bash
cd "/Users/m/Documents/New project/2025_2026-introduction-in-web-tech-k66666-filianin_i_v"
python -m pip install mkdocs mkdocs-material
python -m mkdocs serve
```

После запуска сайт доступен по адресу `http://127.0.0.1:8000/`.

## Сборка

```bash
python -m mkdocs build
```

Собранные статические файлы появляются в папке `site/`.
