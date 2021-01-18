# MSP4_sandbox
# MSP4 sand box

## Install django
```pip3 install django```

> Installing collected packages: sqlparse, pytz, asgiref, django
> Successfully installed asgiref-3.3.1 django-3.1.5 pytz-2020.5 sqlparse-0.4.1

```django-admin startproject msp4_sandbox```

From [pwd] /workspace/MSP4_sandbox:

```cd msp4_sandbox```

 
```python3 manage.py runserver```

Port #8000 made public.

>You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
>Run 'python manage.py migrate' to apply them.

```python3 manage.py migrate```

### Apps

```python3 manage.py startapp msp4```

Creates a subdirectory : msp4.
With python files:
- admin.py
- apps.py
- models.py
- tests.py
- views.py



## Gitpod Reminders

To run a frontend (HTML, CSS, Javascript only) application in Gitpod, in the terminal, type:

`python3 -m http.server`

A blue button should appear to click: *Make Public*,

Another blue button should appear to click: *Open Browser*.

To run a backend Python file, type `python3 app.py`, if your Python file is named `app.py` of course.

A blue button should appear to click: *Make Public*,

Another blue button should appear to click: *Open Browser*.

In Gitpod you have superuser security privileges by default. Therefore you do not need to use the `sudo` (superuser do) command in the bash terminal in any of the lessons.
