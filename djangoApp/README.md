# Django APP

## Steps to create Django APP
```
$ mkdir djangoApp
$ cd djangoApp
$ django-admin.py startproject config .
$ python manage.py runserver
$ pip freeze > requirements.txt
$ docker build -t django .
$ docker run --name django_server -d -p 8000:8000 django:latest
$ docker exec -it django_server /bin/bash
$ lsof -i:8000
$ curl http://localhost:8000
```