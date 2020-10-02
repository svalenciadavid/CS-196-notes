# Django
[**Slides Pt.1**](https://docs.google.com/presentation/d/1FtDonzzUOaQH6YH6T6ZNiJ3KQdQ7J7ytdD9H9itHFj8/edit#slide=id.g247955e1a9_1_0) 

[**Youtube Video Pt.1**](https://www.youtube.com/watch?v=diQvq9ClAiE)

Django is a Web Framework (has a collection of packages or modules), it helps us web applications. It is good because it is, secure, efficient, cheap.

## Model, View, Controller
This is a design pattern used for developing user interfaces. It helps us separate backed from what the user interacts with.

**_Note:_** Django uses MVT (Model-View-Template) which is very similar, enough to call it MVC, only difference is that controller is handled by the framework itself (easier for us)

This process all starts with the request, gets send to controller which decides where it goes, then model talks to controller if it needs to and controller back to view; then we get the presentation.

#### Model(to controller):
Handles data logic and interacts with database

#### Controller(to view and model):
Handles request flow, never handles data logic

#### View:
Handles data presentation, Dynamically rendered (UI/Visual)

## Now, Django!
[Recommended tutorial](https://www.youtube.com/playlist?list=PLsyeobzWxl7r2ukVgTqIQcl-1T0C2mzau), also, read the DOCUMENTATION
[Setup](https://docs.djangoproject.com/en/3.1/)

Django will help us create dynamic websites(tailored to the user) instead of static websites. Our template will use HTML-CSS-JS

### Creating our first project
This command will get us up and running into our new project, by pasting the http address (from bash) into a browser we will get a screen with the message: 
"the install worked successfully"
```bash
$ django-admin startproject <project_name>
$ cd <project>
$ python manage.py runserver
```
Django is  a server side app, it is design to emulate a server so that we can test.

You will see that your folder structure will look like so:

[projectname]/
|- - -> [projectname]/
|- - - - - | -->\_\_init\_\_.py
|- - - - - | --> settings.py
|- - - - - | --> urls.py
|- - - - - | --> wsgi.py
| --> mange.py

* **manage.py file:** is the file Django uses, a command line utility which lets you interact with the Django project

 The actual package is within the only other folder (with the same name), this folder contains:
* **init file:** which is an empty file that lets python know that the directory can be treated as a python package
* **settings file:** which stores all the settings/configs of our project
* **urls file:** which lets us do our **url mapping**, think of this as a table of contents or **index** for all our pages
* **wsgi file:** which is a Web Server Gateway Interface, we need this to deploy the file, it's a standard used for how web servers communicate with web apps.

### Hello world app
We haven't created our application yet, which is why there is no models/views, so let's do it!

This will create a new folder for our app and then create a urls.py file inside of it (the urls page will help us index all our pages and provides relevant mappings to all of them.)
```bash
$ django-admin startapp hello_world
$ cd hello_world/
$ code urls.py
```
We can then code up the file to look like the file below. 
```python
from django.urls import path
from . import views
# When our url has '' (nothing) we want our views to run the home function
urlpatterns = [
	path('', views.home, name="home"),
]
```
In this same directory, we also want to update our views.py file to look like the file below. The request comes from the user (from the controller), then, we return an Http Response with a "hello world" message(We MUST include this).
```python
from django.shortcuts import render
from django.http import HttpResponse

#Create your views here.

def home(request):
	return HttpResponse("Hello World")
```

Now we must update our root urls.py so that it knows about our hello_world/urls.py. The root's .py file takes care of the mapping for the whole project.

we first import the include function and then add an extra path with all the urls from hello_world/urls.py
```python
from django.contrib import admin  
from django.urls import path, include  
  
urlpatterns = [  
    path('admin/', admin.site.urls),
    path('', include('hello_world.urls')),  
]
```

To create large dynamic web pages we will use templates(HTML/CSS/JS also use Django template language). 

We first have to create a directory called templates in the root.
We then update the settings.py file so it knows where the templates will come from.

What we are updating from this file is the DIRS part of the code.
```python
TEMPLATES = [  
    {  
        'BACKEND': 'django.template.backends.django.DjangoTemplates',  
        'DIRS': [os.path.join(BASE_DIR,'<name_of_template_folder>')],  
        'APP_DIRS': True,  
        'OPTIONS': {  
            'context_processors': [  
                'django.template.context_processors.debug',  
                'django.template.context_processors.request',  
                'django.contrib.auth.context_processors.auth',  
                'django.contrib.messages.context_processors.messages',  
            ],  
        },  
    },  
]
```
Now we create an HTML file inside the templates folder (regularly named index.html)
```html
<h1>Hello World! But from a ~file~<h1>
```
Then we update our hello_world/urls.py to **render** our HTML file
```python
def home(request):
	return render(request, 'index.html')
```