# Creating the project
```python
django-admin startproject projectname
```
```
projectname/
    manage.py
    projectname/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```

# Creating the first app

Go to the project folder

```python
python manage.py startapp appname
```
```
appname/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py
```
# Creating the first veiw

Go to the app folder

Modify the __view.py__ file.

```python
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

# Creating the URLconf

Add a __urls.py__ file under the app folder.

Modity the urls.py file

```python
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

# Point to the root URLconf at the appname.urls module

Back to project folder.

Modify the __urls.py__ file under the project folder.

```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
```
The include() function allows referencing other URLconf.  
It chops off whatever part of the URL matched up to that point and sends the remaining string to the included URLconf for further processing.

## When to use include()

You should always use include() when you include other URL patterns. __admin.site.urls__ is the only exception to this.

# Run the development server

```python
python manage.py runserver
```

Go to http://localhost:8000/appname/ in your browser.

# Path()

## path() argument: route

route is a string that contains a URL pattern.  
When processing a request, Django starts at the first pattern in __urlpatterns__ and makes its way down the list, comparing the requested URL against each pattern until it finds one that matches.  
Patterns don't search GET and POST parameters, or the domain name.  
For example, in a request to https://www.example.com/myapp/, the URLconf will look for myapp/. In a request to https://www.example.com/myapp/?page=3, the URLconf will also look for myapp/.

## path() argument: view

When Django finds a matching pattern, it calls the specified view function with an [HttpRequest](https://docs.djangoproject.com/en/2.0/ref/request-response/#django.http.HttpRequest)
 object as the first argument and any "captured" values from the route as keyword arguments.

 ## path() argument:kwargs

 Arbitrary keyword arguments can be passed in a dictionary to the target view.

 ## path() argument: name

 Naming your URL lets you refer to it unambiguously from elsewhere in Django, especially from within templates.  
 __This powerful feature allows you to make global changes to the URL patterns of your project while only touching a single file.__
  
