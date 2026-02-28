University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)
Year: 2025/2026
Group: 466075
Author: Казар Владимир Сергеевич
Lab: Lab0
Date of create: 27.02.2026
Date of finished: -

# Отчёт по лабораторной работе №0

## Цель работы

Создать отдельный репозиторий `devops-lab-kazar`, настроить базовое окружение для работы с Git/GitHub и оформить стартовые файлы проекта.

## Что я делал (пошагово)

1. Создал отдельный репозиторий `devops-lab-kazar` на GitHub.
2. Настроил SSH-ключ для работы с GitHub.
3. Клонировал репозиторий на локальную машину.
4. Добавил файлы `README.md`, `.gitignore`, `CONTRIBUTING.md`.
5. Создал ветку `develop`.
6. Сделал коммит `Initial project setup`.
7. Запушил ветку `develop`, создал Pull Request в `main`.
8. Выполнил merge Pull Request и удалил ветку `develop`.

## Команды и результаты

```bash
ssh -T git@github.com
git clone git@github.com:SENATOROVAI/devops-lab-kazar.git
cd devops-lab-kazar
git checkout -b develop
git add .
git commit -m "Initial project setup"
git push -u origin develop
```

Пример проверочного вывода:

```text
git --version
> git version 2.x.x

git branch
> * develop

git log --oneline -1
> a1b2c3d Initial project setup
```

## Артефакты

- `README.md` с описанием проекта, контактами и планом изучения DevOps
- `.gitignore` со стандартными исключениями
- `CONTRIBUTING.md` с правилами участия

## Ссылка на отдельный репозиторий Lab0

- [devops-lab-kazar](https://github.com/SENATOROVAI/devops-lab-kazar)

## Вывод

Лабораторная работа выполнена: создан отдельный репозиторий, настроен GitHub Flow и подготовлена база для дальнейших DevOps-лабораторных.
