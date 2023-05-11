# Проект Контейнеризация. Docker. Предназначен для легкого развертывания
# готового проекта на любом компьютере, без ошибок и проблем

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