Project Structure
=================

General project structure that includes all the application names:


.. code-block:: text


    ── my-project/
        ├── apps  # collection of features or applications of the project/
        │   ├── app_name  # name of the app/feature directory/
        │   │   ├── apis  # API/Presentation layer/
        │   │   │   ├── serializers  # contains all app feature specific serializers/
        │   │   │   │   └── __init__.py
        │   │   │   ├── validators  # contains all app feature specific validators/
        │   │   │   │   └── __init__.py
        │   │   │   ├── views  # handles the HTTP requests & responses/
        │   │   │   │   └── __init__.py
        │   │   │   ├── __init__.py
        │   │   │   ├── filters.py  # feature specific filters
        │   │   │   ├── paginations.py  # contains app/feature pagination classes or functions
        │   │   │   ├── permissions.py  # app feature specific permissions
        │   │   │   └── urls.py  # contains the urls/endpoints, directing incoming website URLs to the correct function or view.
        │   │   ├── event_handlers  # this contains app/feature specific signals/
        │   │   │   └── __init__.py
        │   │   ├── jobs  # this contains app/feature specific scheduled job/tasks/
        │   │   │   └── __init__.py
        │   │   ├── management # contains custom app/feature commands to run/
        │   │   │   ├── commands/
        │   │   │   │   └── __init__.py
        │   │   │   └── __init__.py
        │   │   ├── middlewares  # contains app/feature middleware functionalities/
        │   │   │   └── __init__.py
        │   │   ├── migrations  # contains all migrations files/
        │   │   │   └── __init__.py
        │   │   ├── selectors  # handles app/feature complex/simple database queries in retrieving data/
        │   │   │   └── __init__.py
        │   │   ├── services  # handles app/feature business rules and orchestration/
        │   │   │   └── __init__.py
        │   │   ├── __init__.py
        │   │   ├── admin.py  # handles register of model classes in admin panel
        │   │   ├── apps.py  # contains configuration class and defines your app's metadata
        │   │   ├── authentication.py  # handles the app/feature authentication
        │   │   ├── exceptions.py  # app/feature specific exception handling
        │   │   ├── models.py  # contains the models/schema classes for database
        │   │   ├── permissions.py  # contains app/feature permissions
        │   │   └── schemas.py
        │   └── __init__.py
        ├── configs  # contains the project configurations/
        │   ├── library_configs  # 3rd party configurations example: celery, aws etc/
        │   │   ├── __init__.py
        │   │   ├── aws.py
        │   │   └── celery.py
        │   ├── settings  # settings for different environments such as development, staging and production/
        │   │   ├── __init__.py
        │   │   ├── base.py  # base parent that contains the project configurations
        │   │   ├── development.py
        │   │   ├── production.py
        │   │   └── staging.py
        │   ├── __init__.py
        │   ├── asgi.py  # connects project to asynchronous web servers
        │   ├── env.py  # project environment script to fetch environment variables from .env file
        │   ├── urls.py  # contains app/feature urls, directing incoming website URLs to the correct app/feature url
        │   └── wsgi.py  # connects project to standard, synchronous web servers
        ├── core  # contains all the system wide or global attributes/
        │   ├── exceptions  # global exceptions and error handling/
        │   │   ├── __init__.py
        │   │   └── base.py
        │   ├── filters  # global filter/
        │   │   ├── __init__.py
        │   │   └── base.py
        │   ├── paginations  # global paginations/
        │   │   ├── __init__.py
        │   │   └── base.py
        │   ├── permissions  # global permissions/
        │   │   ├── __init__.py
        │   │   └── base.py
        │   ├── __init__.py
        │   ├── authentication.py  # global auth
        │   ├── constants.py  # system wide constants
        │   ├── context_processors.py  # system wide context processors (optional)
        │   ├── mixins.py  # system wide mixins (optional)
        │   ├── version.py  # API version
        │   └── swagger.py  # global Swagger API docs
        ├── logging_config  # contains logging configurations/
        │   ├── __init__.py
        │   ├── base.py
        │   ├── development.py
        │   ├── env.py
        │   ├── production.py
        │   └── staging.py
        ├── static  # contains static JS, CSS, SCSS, Images etc (optional)/
        ├── templates  # contains html files (optional)/
        ├── tests  # contains tests functionalities/
        │   ├── test_apps/
        │   │   └── test_app_name  # test all the modules in the app/feature/
        │   ├── test_configs  # test the project configuration/
        │   ├── test_core  # tests all the modules in core//
        │   ├── test_utilities/
        │   ├── __init__.py
        │   └── conftest.py  # Pytest fixtures
        ├── utilities  # shared or global utilities/
        │   └── __init__.py
        ├── .env
        ├── CONTRIBUTION.md
        ├── LICENSE
        ├── manage.py
        ├── pyproject.TOML
        └── README.md


Explanation of why this structure was chosen.
