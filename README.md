# MSP4 sand box

## Install django
```pip3 install django```

> Installing collected packages: sqlparse, pytz, asgiref, django
> Successfully installed asgiref-3.3.1 django-3.1.5 pytz-2020.5 sqlparse-0.4.1

```django-admin startproject msp4_sandbox```

```django-admin startproject django_todo . ```

From [pwd] /workspace/MSP4_sandbox:

```cd msp4_sandbox```

 
```python3 manage.py runserver```

Port #8000 made public.

Runserver called for the first time creates a file db.sqlite3 and a __pycache__ directory.

>You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
>Run 'python manage.py migrate' to apply them.

```python3 manage.py migrate```

### Apps

```python3 manage.py startapp msp4```

```python3 manage.py startapp todo```


Creates a subdirectory : msp4.
With python files:
- admin.py
- apps.py
- models.py
- tests.py
- views.py

#### views.py
``` 
from django.shortcuts import render, HttpResponse
# Create your views here.
def say_hello(request):
    return httpRequest("Hello!")
```

> How do we make this function available to the browser ? 

#### urls.py

```
from django.contrib import admin
from django.urls import path
from todo.views import say_hello

urlpatterns = [
    path('admin/', admin.site.urls),
    path('hello/', say_hello, name="Hello")
]
```

``` python3 manage.py runserver ```

Browser:

- ![Page Not Found](/msp4_sandbox/static/docs/PNF_404.jpg)


``` https://8000-e6ab4b52-9510-4ae0-9182-4eb7e0bfc1e5.ws-eu03.gitpod.io/hello/ ```

- ![Hello](/msp4_sandbox/static/docs/Hello.jpg)



### Templates

Each app can have a templates folder.
Templates allow full html pages to be called by Django, rather than html lines.
It allows incorporation of CSS and JavaScript as well.

1. Go to the app folder and create a templates folder.
2. Within the templates folder create another folder called 'appname' (e.g. todo)
3. Within that directory create an html file, e.g. todo_list.html.

#### views.py

Instead of calling httpresponse with lines of html we can render a page.
```
def get_todo_list(request):
    return render(request, "todo/todo_list.html")
```    

#### urls.py

Now making a 'home' page by putting a blank path.

```from todo.views import say_hello, get_todo_list```


```
urlpatterns = [
    path('admin/', admin.site.urls),
    path('hello/', say_hello, name="Hello"),
    path("", get_todo_list, name="get_todo_list")
    ]
```


#### settings.py
[django_todo/settings.py]
Need to tell django there's a new template in town.

``` 
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'todo',
]
```


- ![ThingsToDo](/msp4_sandbox/static/docs/ThingsINeedTodo.jpg)

### Migrations and admin

Migrations are Django's way of converting python code into database operations.

``` python3 manage.py makemigrations [--dry-run] ```

``` python3 manage.py showmigrations```

``` python3 manage.py migrate [--plan] ```

``` python3 manage.py createsuperuser ``` prompts for 1) username; 2) email; 3) password/confirm password.

### Models




## Gitpod Reminders

To run a frontend (HTML, CSS, Javascript only) application in Gitpod, in the terminal, type:

`python3 -m http.server`

A blue button should appear to click: *Make Public*,

Another blue button should appear to click: *Open Browser*.

To run a backend Python file, type `python3 app.py`, if your Python file is named `app.py` of course.

A blue button should appear to click: *Make Public*,

Another blue button should appear to click: *Open Browser*.

In Gitpod you have superuser security privileges by default. Therefore you do not need to use the `sudo` (superuser do) command in the bash terminal in any of the lessons.
