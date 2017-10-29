Players
=======

``Players`` is a global scope table.


getByPID(pid)
-------------

**Parameters:**
    | **number** pid.
**Return:**
    | :doc:`./player`.

getByGUID(guid)
---------------

**Parameters:**
    | **number** guid.
**Return:**
    | :doc:`./player`.

for_each(func)
--------------

Calls ``function(player)`` for all players.

**Parameters:**
    | **function** func.

.. code-block:: lua

    Players.for_each(function(player)
        player:message("Hello\n")
    end)
    
size()
------

**Return:**
    | **number** The number of online players.
