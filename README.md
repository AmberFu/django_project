# Use Django to build REAT API

### How to start a Django project

Follow [Django Tutorial](https://docs.djangoproject.com/en/3.2/intro/tutorial01/)

```
## Set up a virtual env
$ conda create -n my_django_env python=3.7 django
$ conda activate my_django_env

## Start a Django project
$ django-admin startproject django_project

## Start the server
$ cd django_project
$ python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
June 25, 2023 - 01:47:31
Django version 3.2.15, using settings 'django_project.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
[25/Jun/2023 01:47:38] "GET / HTTP/1.1" 200 10697
[25/Jun/2023 01:47:38] "GET /static/admin/css/fonts.css HTTP/1.1" 200 423
[25/Jun/2023 01:47:38] "GET /static/admin/fonts/Roboto-Bold-webfont.woff HTTP/1.1" 200 86184
[25/Jun/2023 01:47:38] "GET /static/admin/fonts/Roboto-Light-webfont.woff HTTP/1.1" 200 85692
[25/Jun/2023 01:47:38] "GET /static/admin/fonts/Roboto-Regular-webfont.woff HTTP/1.1" 200 85876
Not Found: /favicon.ico
[25/Jun/2023 01:47:38] "GET /favicon.ico HTTP/1.1" 404 2118


```
