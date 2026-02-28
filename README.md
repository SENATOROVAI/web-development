# 2025-introduction-in-web-tech-466075-kazar_v_s

Персональный сайт Казара Владимира Сергеевича, выполненный в рамках курсовой работы по дисциплине «Введение в веб технологии».

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
cd <папка_проекта>
python -m pip install mkdocs mkdocs-material
python -m mkdocs serve
```

Сайт будет доступен по адресу `http://127.0.0.1:8000/`.

## Сборка

```bash
python -m mkdocs build
```

Собранные статические файлы появляются в папке `site/`.
