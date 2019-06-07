# Docker Django-Postgres Skeleton

## How to use it?

1. Import the docker folder and the docker-compose.yml file at the root of your Python-Postgre project.

2. Create a new Django project using _django-admin startproject NAME_.

3. Create the _requirements.txt_ file a the root of your project to let pip install your dependencies when running the image.

4. Into the project, find the _settings.py_ file and replaces the _DATABASES_ config by this one (or another, depending on your env) : 

~~~~
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': '5432',
    }
}
~~~~

5. Make sure _root_ has executions privileges on your _.sh_ files.

6. To deploy your server (to port 8000 with this config), just the command :
~~~
docker-compose up -d --build
~~~

7. To stop the server, just run :
~~~
docker-compose down
~~~

## What does it do?

This Skeleton automatically does multiple things for you :

- It creates a container for the database, using a Docker Hub image.
- It creates a container containing your Django application
- It creates a container running the database migrations at startup. This step allows the Django container to do one thing only and follows the Docker guidelines.
- It initializes and run all three containers using _docker-compose_.