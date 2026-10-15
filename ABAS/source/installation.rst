Installation Guide
==================

🚀 Step 1: Installing Poetry
----------------------------

If Poetry is not installed on your machine, run the following command:

.. code-block:: bash

   curl -sSL https://install.python-poetry.org | python3 -

📝 You may need to restart your terminal or run export to use the poetry command:

.. code-block:: bash

   PATH="$HOME/.local/bin:$PATH"

Alternatively, you can install Poetry using ``pipx`` or ``pip``.

Check the version:

.. code-block:: bash

   poetry --version


📂 Step 2: Clone the Project (if applicable)
--------------------------------------------

.. code-block:: bash

   git clone https://github.com/your-username/your-django-project.git
   cd your-django-project


🧰 Step 3: Set Up the Environment with Poetry
---------------------------------------------

1. Install project dependencies:

   .. code-block:: bash

      poetry install

2. Activate the virtual environment:

   .. code-block:: bash

      poetry shell

3. (Optional) If you're not using ``poetry shell``, you can run any command within the virtual environment using:

   .. code-block:: bash

      poetry run python manage.py runserver


⚙️ Step 4: Set Up Django
-------------------------

1. Set up ``.env`` file in the Django project: see :ref:`configuration` section.


2. Create migrations:

   .. code-block:: bash

      python manage.py makemigrations

3. Apply migrations:

   .. code-block:: bash

      python manage.py migrate

4. Run the development server:

   .. code-block:: bash

      python manage.py runserver

Access the project in your browser at http://127.0.0.1:8000 or at the domain name you configured.


🔧 Step 5: Useful Commands
--------------------------

Here are some additional commands you may need:

- **Run Celery worker**:

  .. code-block:: bash

     poetry run celery -A <project name> worker --loglevel=info --pool=solo --concurrency=<concurrency number of your choice>

- **Run Celery beat scheduler**:

  .. code-block:: bash

     poetry run celery -A <project_name> beat --loglevel=info --scheduler django_celery_beat.schedulers.DatabaseScheduler

- **Run Flower for monitoring Celery tasks**:

  .. code-block:: bash

     poetry run celery -A <project_name> flower --port=5555

- **Collect static files (for Django)**:

  .. code-block:: bash

     python manage.py collectstatic

- **Run tests**:

  .. code-block:: bash

     poetry run pytest

- **Run Alert Storage Schedule**:

  .. code-block:: bash

     python manage.py setup_alert_storage_schedule

- **Run Retry Azure Creation**:

  .. code-block:: bash

     python manage.py setup_integrations_schedule

- **Run Download Records Schedule**:

  .. code-block:: bash

     python manage.py setup_download_records

