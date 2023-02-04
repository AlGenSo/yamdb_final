# yamdb_final
**Проект: CI и CD проекта api_yamdb**
---
---
### Описание
##### Идея проекта
Проект YaMDb собирает отзывы пользователей на произведения.
Здесь нельзя посмотреть фильм или послушать музыку.
Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка».
##### Задача проекта
Настроить для приложения Continuous Integration и Continuous Deployment.

Реализовать: 
- автоматический запуск тестов
- обновление образов на Docker Hub
- автоматический деплой на боевой сервер при пуше в главную ветку main
- отправка уведомления в Telegram о том, что процесс деплоя успешно завершился
---
### Технологии:
- Django 
- Django REST Framework
- Django Filter
- PyJWT
- Docker
- PostgreSQL
- Nginx
- Gunicorn
- DockerHub
- Yandex.Cloud
---

### Статус workflow
[![Yamdb_final workflow](https://github.com/AlGenSo/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)](https://github.com/AlGenSo/yamdb_final/actions/workflows/yamdb_workflow.yml)
---
---

##### Запуск проекта

* _Клонировать репозиторий: `git clone` git@github.com:AlGenSo/yamdb_final.git_
* _Перейти в него в командной строке: `cd yamdb_final/`_
* _Перейти в папку infra: `cd infra`_
* _Создать файл .env, с параметрами:_
    ```
    DB_ENGINE=django.db.backends.postgresql
    DB_NAME=postgres
    POSTGRES_USER=postgres
    POSTGRES_PASSWORD=postgres
    DB_HOST=db
    DB_PORT=5432
    ```

### Разработчик проекта:
##### Солодовников Александр
---