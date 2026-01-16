# Django
    * Created one year after I was born - 2003. 
    * Free and open-source Python web framework that runs on a web server.

    # Starting a new Project using the Terminal
        1. Creating the Project: 'django-admin startproject learning_log .'
            * Don't forget to add the dot at the end.

        2. Creating the Database: 'python manage.py migrate'
            * Django stores most of the data/information in a database so that is next. 

        3. Viewing the Project: 'python manage.py runserver'
            * Look at #manage.py for more details.
# learning_log (PROJECT FOLDER)
    * Holds contents of the project, knows about the apps, and handles global and routing.

    # manage.py

        Viewing the Project (Terminal): "python manage.py runserver"
        * Starts a server called the development server, so you can view the project
        on your system to see how well it works.
        1. Check if project is setup correctly.
        2. Reports version of Django in use and name of settings file in use.
        3. Reports the URL where the project is being served: http://127.0.0.1:8000/
        * Port 8000 is your computers local host. Referring to a server that only processes requests on
        your system.

            Errors connecting to server:
            * Try a different port number by entering this command: "python manage.py runserver 8001",
            which will go ahead and run a server or port 8001.

        Activating Models / Modifying Models (Terminal): 
        * Follow these steps to either activate or modify the models you've created. Make migrations and then migrate. 
        1. "python manage.py makemigrations filename_logs"
        2. "python manage.py migrate filename_logs"
        * makemigrations: how to modify database so it can store the data associated with any new models we've defined. Django creates a migration file
        called '0001_initial.py'. This migration creates a table for the model Topic in the database.
        * migrate: applies the migration and has Django modify the database. Confirming it the migration worked for the file name.

            Errors activating entry/making migrations:
            * Verify models.py doesn't have any wrong syntax.
            * Verify terminal syntax.

        Creating a Superuser (Terminal): "python manage.py createsuperuser"
        * To effectively run a website you need an administrator to handle sensitive and background information. There are administrators that do that and 
        regular user priveleges actions that are controlled by the admin. 
        * When creating a superuser it prompts you with the following: 
            Username:
            Email:
            Password:
        *Passwords are stored in a string derived from the password as a hash.
            hash - is a function that changes data using an algorithm to a fixed-length output
            ex: hash("dog") → cd6357efdd966de8c0cb2f876cc89ec74ce35f0968e11743987084bd42fb8944
            

    # settings.py
        Settings about overall project. Has settings regarding all apps, security, keys,
        databases, time zone, language, etc.

        In the list of Installed apps, we added our model which is under the file 'learning_logs', so we added a brief section above the default apps
        to distinguish the difference between the two.

    # wsgi.py
        web server gateway interface
        * Helps Django serve the files it creates

    # urls.py
        uniform resource locator: address of something on the internet
        * Tells Django which pages to build in response to browser requests
        * This file is used to manage URLs for the admin site
        * Represents the project as a whole

    # db.sqlite3
        SQLite is a database that runs off a single file. Ideal for writing simple apps that manage 
        a small database with low management.

# learning_logs (STARTAPP NAME, ONE OF MANY APP FOLDERS)
    * A feature / model

    # models.py
        * Defines the data we want to manage in our app.
        * A model tells Django how to work with the data that will be stored in the app. 
        
        Attributes for Models (module)
            CharField - a piece of data that's made up of characters or text. To store a small amount of text.
            ex: Name, Title, City, etc. When it is defined we tell Django how many characters make up the CharField.
            code ex: "text = models.CharField(maxLength=200)"

            DateTimeField, piece of data that will record a data and a time. Passing the argument auto_now_add=True,
            which tells Django to AUTOMATICALLY set this attribute to the current DATE and TIME whenever the user creates a new topic NOW.
            code ex: "date_added = models.DateTimeField(auto_now_add=True)"

            models.ForeignKey(Topic,on_delete=models.CASCADE) - A foreign key: database term that references another record in the database.
            Connecting each key entry to a specific topic assigning a key / ID to a topic. The 'on_delete=models.CASCADE' tells
            Django when a topic is deleted that anything associated with it will be deleted as well. --> cascading delete.

    # admin.py
        * Register models to the admin site.

        Attributes to Register Models (module)
            admin.site.register(MODEL_NAME) - manage the model through the admin site
        
        *Anytime we activate a model we follow these steps:
            1. Create / Modify Model
            2. Make Migrations to 'app_name'
            3. Migrate the change.
            4. Register Entry to Admin site in admin.py

    # urls.py
        * Defines URL Patterns for learning_logs
        * We define URL pattern for the index / homepage for the project.

        Attributes for Path (module):
            path('', views.index, name='index')

                Takes three arguments:
                1. String that Django routes the current request properly.
                2. Specifies which function to call in views.py
                3. Provides the name index for the URL pattern to refer in other code sections.

        Errors you may come across: File "/usr/local/python/3.12.1/lib/python3.12/site-packages/django/urls/resolvers.py", line 739, in url_patterns
        raise ImproperlyConfigured(msg.format(name=self.urlconf_name)) from e django.core.exceptions.ImproperlyConfigured: The included URLconf '<module 'learning_logs.urls' from '/workspaces/web-journal-system/learning_logs/urls.py'>' does not appear to have any patterns in it. If you see the 'urlpatterns' variable with valid patterns in the file then the issue is probably caused by a circular import.

            How I fixed it: Incorrect syntax in file name '/learning_logs/urls.py'. Just keep an eye out on syntax.
# The Django API
    # Website to understand Queries: https://docs.djangoproject.com/en/6.0/topics/db/queries/