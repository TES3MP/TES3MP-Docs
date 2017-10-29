ModInfo
=======

ModInfo table should contain basic info about a script addon:

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

The name of the script addon without spaces.

author
------

version
-------

The version used in the dependency checker.

dependencies
------------

The table of dependencies.
