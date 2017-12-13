moduleInfo.json
===============

moduleInfo.json should contain basic info about a script addon:

.. code-block:: json

    {
        name: "MyFirstMod",
        author: "Me",
        version: "0.0.1",
        dependencies: {
            "Core": ">=0.0.1",
            "MyAnotherMod": ">=0.0.1"
        }
    }

name
----

The name of the script addon without spaces.

author
------

The name of the author.

version
-------

The version used in the dependency checker.

dependencies
------------

The list of dependencies.
