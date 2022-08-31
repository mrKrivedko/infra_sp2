Сборка докер контейнера для проекта apy_yamdb.
Проект YaMDb собирает отзывы (*Review*) пользователей на произведения (*Titles*).

- для сборки контейнера запустить комманду  _docker-compose up -d --build_

в папке *infra* размкщается файл .env 
В файле переменные для settings.py: *SECRET_KEY настройки для postgresql*:
- DJANGOKEY='..'
- DB_ENGINE='..'
- DB_NAME='..'
- POSTGRES_USER='..'
- POSTGRES_PASSWORD='..'
- DB_HOST='..'
- DB_PORT='..'

- после сборки контейнера выполнить миграции: _docker-compose exec web python manage.py migrate_
- после сборки контейнера выполнить миграции: _docker-compose exec web python manage.py createsuperuser_
- после сборки контейнера выполнить миграции: _docker-compose exec web python manage.py collectstatic --no-input_
- для загрузки дампа:  _docker-compose exec web python manage.py loaddata fixtures.json_