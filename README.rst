DJ-JSON-ENV
~~~~~~~~~~~

.. image:: https://badge.fury.io/py/dj-json-env.svg
    :target: https://badge.fury.io/py/dj-json-env
    
This is a simple django utility to read local configuration from JSON formated
string specified in environment variable or local file.

Installation
------------

Installation is simple::

    $ pip install dj-json-env

Usage
-----

Create a file ``local_settings.py``

Setup ``LOCAL_SETTINGS`` environment variable by usig ``export_json`` command::

    $ export LOCAL_SETTINGS=`export_json -m "local_settings"`


Configure your variable in ``settings.py`` from ``env.LOCAL_SETTINGS``::

    import dj_json_env

    local_settings = dj_json_env.parse("LOCAL_SETTINGS")

    DEBUG = local_settings.get("DEBUG", True)

