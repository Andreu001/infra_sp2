# Проект Контейнеризация. Docker. Предназначен для легкого развертывания
# готового проекта на любом компьютере, без ошибок и проблем

### шаблон наполнения env-файла:
```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=0664487 # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
```
### Cоздать и активировать виртуальное окружение:
```angular2html
python -m pip install --upgrade pip
pip install -r requirements.txt
```
### Выполнить миграции:
```angular2html
python manage.py migrate
```
### Запустить проект:
```angular2html
python manage.py runserver
```
### Команды для заполнения базы данными
###копируем файл с базами данных из /infra в папку app
```angular2html
docker cp fixtures.json id_контенера:/app
```
### запускаем команду для загрузки баз
```angular2html
docker-compose exec web python manage.py loaddata fixtures.json
```