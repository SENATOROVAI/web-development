University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)
Year: 2025/2026
Group: 466075
Author: Казар Владимир Сергеевич
Lab: Lab2
Date of create: 27.02.2026
Date of finished: -

# Отчёт по лабораторной работе №2

## Цель работы

Настроить CI/CD для Docker-приложения: автоматическую сборку и публикацию образа в Docker Hub через GitHub Actions.

## Что я делал (пошагово)

1. Скопировал из Lab1 файлы `app.py`, `requirements.txt`, `Dockerfile`.
2. Создал workflow `lab2/.github/workflows/docker-build.yml`.
3. Настроил запуск пайплайна на `push` в ветки `main` и `develop`.
4. Добавил шаги `checkout`, `buildx`, `login`, `build-and-push`.
5. Настроил условные шаги деплоя:
   - `main` -> production;
   - `develop` -> development.
6. Добавил секреты репозитория: `DOCKER_USERNAME`, `DOCKER_PASSWORD`.
7. Проверил выполнение workflow в GitHub Actions после push.

## Команды и результаты

```bash
git add .
git commit -m "Add CI/CD workflow for docker build and push"
git push origin develop
# после merge
git push origin main
```

Ожидаемый результат в Actions:

```text
Workflow: Docker Build and Deploy
Branch: develop/main
Status: Success
Step "Build and push image": completed
```

Ожидаемый результат в Docker Hub:

```text
Repository: <DOCKER_USERNAME>/my-flask-app
Tag: latest
Updated: after last successful pipeline run
```

## Проверка условий со звездочкой

- для `develop`: вывод `Deploying to development server...`;
- для `main`: вывод `Deploying to production server...`.

## Вывод

CI/CD пайплайн настроен: сборка и публикация Docker-образа автоматизированы, деплой зависит от целевой ветки.
