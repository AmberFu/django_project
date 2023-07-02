# TDD Django with RESTful API

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

### Creating the Polls app (follow the tutorial)

```
## Create a polls APP
$ ls
db.sqlite3  django_project  manage.py  README.md

$ python manage.py startapp polls

$ ls
db.sqlite3  django_project  manage.py  polls  README.md
 
$ ls polls 
admin.py  __init__.py  models.py  views.py
apps.py   migrations   tests.py

```

### Write your first view - Edit `polls/views.py`

```
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")

```
This is the simplest view possible in Django. 

To call the view, we need to map it to a URL - and for this we need a URLconf.

To create a URLconf in the polls directory, create a file called `urls.py`. Your app directory should now look like:

```
polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    urls.py
    views.py
```

In the `polls/urls.py` file include the following code:

```
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

The next step is to point the root URLconf at the `polls.urls` module. 

In `mysite/urls.py`, add an import for `django.urls.include` and insert an include() in the urlpatterns list, so you have:

```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]

```
The include() function allows referencing other URLconfs.

You have now wired an index view into the URLconf. Verify it’s working with the following command:

```
$ python manage.py runserver

```
