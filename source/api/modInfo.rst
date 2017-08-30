ModInfo
=======

ModInfo table should contain basic info about mod:

.. code-block:: lua

    ModInfo = {
        name = "MyFirstMod",
        author = "Me",
        version = "1.2.3",
        dependencies = {
            {"Core", ">=0.0.1"},
            {"MyAnotherMod", ">=0.1.0"}
    }

ModInfo should be placed at the top of ``main.lua``.

name
----

Name of mod without spaces.

author
------

version
-------

version used in dependency checker

dependencies
------------

Table with dependencies
