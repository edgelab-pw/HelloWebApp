# Starting your Django project

You've installed Python and the other utilities (pip, virtualenv, and git) on
your computer, right? If not, [head here to
install](https://github.com/limedaring/HelloWebApp/tree/master/installation-instructions).

First thing we need to do is create a folder for your project. I personally use
a "projects" folder in my top level user folder on my computer, which contains
all my programming projects. If you'd like to do this as well, follow these
commands in your terminal to create the projects folder, and a folder within for
this individual project:

```
mkdir projects
cd projects
mkdir hellowebapp
```

If you need a command line review, `mkdir` creates folders, and `cd` changes
directories into that folder. If you ever get lost, your terminal should show
what directory your in, and running `ls` (on Mac or Linux, `dir` on Windows),
will list out the contents of the folder you're in. Use `cd ..` to back up out
of a folder.

### Start your virtual environment

Now that you're within your empty project folder, create your virtual
environment using virtualenv with this command:

```
virtualenv --distribute venv
```

And then activate the environment:

```
source venv/bin/activate
```

Now you're in your bubble so we can start installing project specific utilities.
If you ever need to deactivate your environment, run `deactivate`.

### Install Django

Finally it's Django time! We'll use pip to install Django, so run this in your
command line, making sure you're in your project folder and the virtual
environment is activated:

```
pip install Django==1.6.2
```

We're telling pip to install a specific version of Django, in case Django
releases a new version that this tutorial doesn't cover.

### Start git

We also want to start our version control system. Now that we're in our project
folder, run this command to start git:

```
git init
```

### Start your Django project

We installed Django, now we can use Django to build all the starting files we
need for our web app. In your command line (again, in your project folder with
your environment activated):

```
django-admin.py startproject hellowebapp .
```

This is going to start a Django project in your currect directory. 

* django-admin.py: The script we'll be running.
* startproject: the specific utility we're using.
* hellowebapp: The name we're giving the project.
* . : The location where we're starting the project, with `.` denoting the
  current directory.

`startproject` will create these files and folders:

```
hellowebapp/
    manage.py
    hellowebapp/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```

The hellowebapp folder is your top level folder. 

* `manage.py`: We won't edit this file, but will use this file in the command line
  to interact with your project. You'll see it in action soon.
* The inner `hellowebapp` folder holds your project.
* `__init__.py`: Ignorable - tells Python and that this is a Python package.
* `settings.py`: Aptly named - contains your settings.
* `urls.py`: URL declarations for the project. Important and we'll go over this
  soon.
* `wsgi.py`: Not needed at this point until you deploy your project.

## Run your Django web app

Want to see if everything worked? In your terminal, head over to your top level
hellowebapp folder, and run this command:

```
python manage.py runserver
```

...and you'll see the local Django development server starting, which'll serve
your project to your computer.

```
Validating models...

0 errors found
March 26, 2014 - 15:50:53
Django version 1.6, using settings 'mysite.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```

Now just head to your favorite web browser, and visit http://localhost:8000 and
you'll see a "Welcome to Django" page. Congrats on starting Django!
