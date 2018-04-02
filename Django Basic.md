# Django Basic

## URL, Uniform Recource Locator

The __Uniform Resource Locator(URL)__ defines a unique link to get resources such as an HTML page, picture
## MVC, Model-View-Controller
* __Models__: These represent data organization in a database. A model defines a table and the relations between other models. Every bit of data is stored in the database.
* __Views__: These contain all the information that will be sent to the client. We can associate the HTML code with the views.
* __Controllers__: These contain all the actions performed by the server and are not visible to the client. The controller checks whether the user is authenticated or it can generate the HTML code from a template.
```
1. The client sends a request to the server asking to display a page.
2. The controller uses a database through models. It can create, read, update, or delete any record or apply any logic to the retrieved data.
3. The model sends data from the database; for example, it sends a product list if we have an online shop.
4. The controller injects data into a view to generate it.
5. The view returns its content depending on the data given by the controller.
6. The controller returns the HTML content to the client.
```
### Django vision
> views are replaced by templates and controllers are replaced by views.

> HTML code will be templates, and our Python code will be views and models.
## Create a project

> A project is considered a Django installation with some settings. n 

```Python
django-admin startproject testsite
```

## Project structure

```
testsite/
    manage.py
    testsite/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```

* __manage.py__: 
1. A command-line utility to interact with your project. (used for actions performed on the project).
>starting the development server or synchronizing the database with the models.
2. A thin wrapper for __django-admin.py__

* __\_\_init\_\_.py__: tells Python to treat the __mysite__ direcotry as a Python __module__.

* __settings.py__: Settings and configuration for your project
> We use it to define the debug mode, configure the database,or define Django packages that we will use.
* __urls.py__: The place where your URL patterns live. Each URL is mapped to a view
* __wsgi.py__: Configuration to run your project as a __WSGI application__.

## Creating an application

>An application is a group of models, views, templates, and URLs.

* We will not program our application in the site folder because we want to create our own task application.

```python
manage.py startapp TestTasks
```

* admin.py: It contains the models that need to be incorporated in the administration module.
* migrations : This directory will contain database migrations of your application. Migrations allow Django to track your model changes and synchronize the database accordingly.
* models.py: It contains all the models of our application. Models allow us to create our database and store information.
* tests.py: It contains the unit tests of our application.
* views.py: It can contain views, all the actions before sending the HTML page to the client. The logic of your application.

## Configuring settings.py

* __DEBUG :__If set to True, Django will display detailed error pages.
> NEVER deploy a site into production with DEBUG turned on because you will expose sensitive data of your project.

* __TIME_ZONE :__ This parameter sets the region refrring to which it must calculate dates and times.The default is __UTC__.


* __DEFAULT_CHARSET :__ This sets the character encoding used.

> DEFAULT_CHARSET = 'utf-8'

* __LANGUAGE_CODE :__This sets the language to be used on the website.

* __MIDDLEWARE_CLASSES :__ It is a tuple containing middlewares to be executed.
> Middleware are classes and methods, including the methods that are performed during the request process.

* __ALLOWED_HOSTS :__ Once you are going to move your site to production and set DEBUG to __False__, you will have to add your domain/host to this setting in order to allow it to serve the Django site.

* __INSTALLED_APPS :__ This setting tells Django which applications are active for this site.  
>By default:  
>>django.contrib.admin : This is an administration site.  
>>django.contrib.auth : This is an authentication framework.  
>>django.contrib.contenttypes : This is a framework for content types.  
>> django.contrib.sessions : This is a session framework.  
>> django.contrib.messages : This is a messaging framework.  
>> django.contrib.staticfiles : This is a framework for managing static files.

* __ROOT_URLCONF :__ It indicates the Python module where the root URL patterns of your application are defined.
>  The syntax means that Django takes the URLs in the __urls.py__ file contained in the __testsite__ package to the root of the project.  
>> The routing of our application will be based on this file. The routing defines how ther client request will be treated based on the URL sent.

* __DATEBASES :__ This is a dictionary containing the settings for all the databases to be used in the project.
> The default configuration uses a SQLite3 database.


 