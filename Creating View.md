## Development Server

```python
manage.py runserver 127.0.0.1:8000
```

__127.0.0.1 : __ it is our internal IP address to the network adapter. This means that our server will listen and respond only to the computer on which it is launched. If we were in a local network and wanted to make our website available on computers other than ours, we would enter our local IP address instead of 127.0.0.1. The value 127.0.0.1 is the default value of the parameter.

__8000 :__ this defines the listening port of the server. This setting is useful to run multiple web servers on a single computer.


## Add an index page

* Add ```url (r'^$', 'TasksManager.views.index.page'), ``` in __url.py__

* In our __index.py__ of __TestTasks__, we will create a method called __page()__
> * This method will return an HTML page to the client.  
> * The page is being returned by the HTTP protocol, so we use the __HttpResponse()__ function and its importation.
> * The argument of this __HttpResponse()__ function returns the HTML content that we will return to the browser.

```python
# - * - Coding: utf -8 - * -
from django.http import HttpResponse
# View for index page.
def page (request) :
 return HttpResponse ("Hello world!" )
```