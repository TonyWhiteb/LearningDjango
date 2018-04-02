# Routing in Django

* When the controller receives the client request, it will go in the __urls.py__ file and check whether the URL is a customer's request and use the corresponding view.

```python
from django.conf.urls import patterns, include, url
from django.contrib import admin
admin.autodiscover()
urlpatterns = patterns('',
    # Examples:
    # url(r'^$', 'Work_msanager.views.home', name='home'),
    # url(r'^blog/', include('blog.urls')),
    url(r'^admin/', include(admin.site.urls)),
)
```

> After having received a request from a web client, the controller goes through the list of URLs linearly and checks whether the URL is correct with regular expressions.  
>>If it is not in conformity, the controller keeps checking the rest of the list.  
>> If it is conformity, the controller will call the method of the corresponding view by sending the parameters in the URL.