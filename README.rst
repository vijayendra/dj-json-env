DJ-JSON-ENV
~~~~~~~~~~~

This is a simple django utility to read local configuration from JSON formated
string specified in environment variable or local file.

Installation
------------

Installation is simple::

    $ pip install dj-json-env

Usage
-----

Configure your variable in ``settings.py`` from ``env.LOCAL_SETTINGS``::

    import dj_json_env

    local_settings = dj_json_env.parse("LOCAL_SETTINGS")

    DEBUG = local_settings.get("DEBUG", True)

