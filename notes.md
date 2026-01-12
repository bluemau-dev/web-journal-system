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

    Errors connecting to server:
    * Try a different port number by entering this command: "python manage.py runserver 8001",
    which will go ahead and run a server or port 8001.

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