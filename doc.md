# Structure
```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```

## __manage.py__
A command-line utility that lets you interact with this Django project.
[django-admin and manage.py](https://docs.djangoproject.com/en/2.0/ref/django-admin/)

## __inner mysite/__
This is the actual Python package for your project.  
Its name is the Python project name you use to import anything inside it(e.g. __mysite.urls__)

### __mysite/settings.py__
Configuration for this Django project. [Django settings](https://docs.djangoproject.com/en/2.0/topics/settings/)

### __mysite/urls.py__
The URL declarations for this Django project.  
A "table of contents" of your Django-powered site.
[URL dispatcher](https://docs.djangoproject.com/en/2.0/topics/http/urls/)

### __mysite/wsgi.py__
An entry-point for WSGI-compatible web servers to serve your project.
[How to deploy with WSGI](https://docs.djangoproject.com/en/2.0/howto/deployment/wsgi/)


