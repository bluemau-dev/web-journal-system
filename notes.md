# Django
    * Created one year after I was born - 2003. 
    * Free and open-source Python web framework that runs on a web server.

# learning_log (PROJECT NAME)
    # manage.py

    Viewing the Project (Terminal): "python manage.py runserver"
    * Starts a server called the development server, so you can view the project
    on your system to see how well it works.
    1. Check if project is setup correctly.
    2. Reports version of Django in use and name of settings file in use.
    3. Reports the URL where the project is being served: http://127.0.0.1:8000/
    * Port 8000 is your computers local host. Referring to a server that only processes requests on
    your system.

    Activating Models / Modifying Models (Terminal): 
    * Follow these steps to either activate or modify the models you've created. Make migrations and then migrate. 
    1. "python manage.py makemigrations filename_logs"
    2. "python manage.py migrate filename_logs"
    * makemigrations: how to modify database so it can store the data associated with any new models we've defined. Django creates a migration file
    called '0001_initial.py'. This migration creates a table for the model Topic in the database.
    * migrate: applies the migration and has Django modify the database. Confirming it the migration worked for the file name.



    Errors connecting to server:
    * Try a different port number by entering this command: "python manage.py runserver 8001",
    which will go ahead and run a server or port 8001.

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

    # db.sqlite3
    SQLite is a database that runs off a single file. Ideal for writing simple apps that manage 
    a small database with low management.

# learning_log (STARTAPP NAME)
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

