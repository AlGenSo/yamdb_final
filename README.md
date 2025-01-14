# yamdb_final
**Проект: CI и CD проекта api_yamdb**
---
---

### Проект доступен
[Adminka](http://158.160.3.56/admin/)

[ReDoc](http://158.160.3.56/redoc/)

ip 158.160.3.56

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
* _Заполнить на github, в разделе Settings >> Secret and variables >> Actions, вкладка Secrets, secret-переменными:_

    _Названия ключей:_
    ~~~
    DB_ENGINE # значение из файла .env
    DB_NAME # значение из файла .env
    DB_PORT # значение из файла .env
    DOCKER_PASSWORD # значение из файла .env
    DOCKER_USERNAME # значение из файла .env
    HOST # значение из файла .env
    POSTGRES_USER # значение из файла .env
    SSH_KEY
        _Скопируйте приватный ключ с компьютера, имеющего доступ к боевому серверу:_
        cat ~/.ssh/id_rsa
        _сохраните ключ в переменную (полностью, со всеми ---)_
    DB_HOST # IP-адрес вашего сервера
    PASSPHRASE # если при создании ssh-ключа вы использовали фразу-пароль
    POSTGRES_PASSWORD
    TELEGRAM_TO # ID своего телеграм-аккаунта
    TELEGRAM_TOKEN # токен вашего бота
    USER # имя пользователя для подключения к серверу
    ~~~

##### Запуск локально

* _Собрать образ при помощи docker-compose: $ docker-compose up -d --build_
* _Выполнить по почереди следующие команды:_

    _Замечание: При использовании ОС Win 11 Home, некоторые команды не проходят без префикса winpty (например, при создании суперюзера)_

~~~
docker-compose exec web python manage.py migrate # Выполнить миграции
docker-compose exec web python manage.py createsuperuser # Создать суперюзера
docker-compose exec web python manage.py collectstatic --no-input # Собрать статику
~~~

[ReDoc](http://localhost/redoc/)
---

##### Запуск на сервере
* _Выполнить push на github_
* _Войти на сервер:_
    ~~~
    ssh <имя-пользователя>/<ip-servers>
    ~~~
* _Вывести контейнеры: sudo container ls_
* _Войти в bash контейнера web: sudo docker exec -it <ID> bash_
* _И выолнить команды:_
~~~
python manage.py migrate # Выполнить миграции
python manage.py createsuperuser # Создать суперюзера
python manage.py collectstatic --no-input # Собрать статику
~~~
---
---

### Разработчик проекта:
##### Солодовников Александр
---