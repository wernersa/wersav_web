

===============================
WerSav
===============================

.. image:: https://travis-ci.org/wernersa/wersav_web.svg?branch=master
     :target: https://travis-ci.org/wernersa/wersav_web
     :alt: Tests

.. image:: https://codecov.io/gh/wernersa/wersav_web/coverage.svg?branch=master
     :target: https://codecov.io/gh/wernersa/wersav_web/
     :alt: Coverage

.. image:: https://pyup.io/repos/github/wernersa/wersav_web/shield.svg
     :target: https://pyup.io/repos/github/wernersa/wersav_web/
     :alt: Updates
     
.. image:: https://pyup.io/repos/github/wernersa/wersav_web/python-3-shield.svg
     :target: https://pyup.io/repos/github/wernersa/wersav_web/
     :alt: Python 3


About
------

This website was built using the boilerplate `Cookiecutter-flask <https://github.com/sloria/cookiecutter-flask>`_.


Quickstart
----------

First, set your app's secret key as an environment variable. For example,
add the following to ``.bashrc`` or ``.bash_profile``.

.. code-block:: bash

    export WERSAV_SECRET='something-really-secret'

Before running shell commands, set the ``FLASK_APP`` and ``FLASK_DEBUG``
environment variables ::

    export FLASK_APP=/path/to/autoapp.py
    export FLASK_DEBUG=1

Then run the following commands to bootstrap your environment ::

    git clone https://github.com/wernersa/wersav
    cd wersav
    pip install -r requirements/dev.txt
    bower install
    flask run

You will see a pretty welcome screen.

Once you have installed your DBMS, run the following to create your app's
database tables and perform the initial migration ::

    flask db init
    flask db migrate
    flask db upgrade
    flask run


Deployment
----------

In your production environment, make sure the ``FLASK_DEBUG`` environment
variable is unset or is set to ``0``, so that ``ProdConfig`` is used.


Shell
-----

To open the interactive shell, run ::

    flask shell

By default, you will have access to the flask ``app``.


Running Tests
-------------

To run all tests, run ::

    flask test


Migrations
----------

Whenever a database migration needs to be made. Run the following commands ::

    flask db migrate

This will generate a new migration script. Then run ::

    flask db upgrade

To apply the migration.

For a full migration command reference, run ``flask db --help``.
