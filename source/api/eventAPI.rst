=========
Event API
=========

Event
=====

``Event`` is global spaced table.

register(eventId, callback)
---------------------------

**Parameters:**
    | **number** eventId. Can be :ref:`created <EventCreate-anchor>` or used :ref:`core event <CoreEvents-anchor>`
    | **function** callback.

Places a new event at the end of the list of events.

.. code-block:: lua

    Event.register(Events.ON_POST_INIT, function()
        print("Server initialized.")
    end)

stop(eventId)
-------------

Stops iterating specified event in other callbacks

**Parameters:**
    | **number** eventId.

.. code-block:: lua

    Event.register(Events.ON_POST_INIT, function()
        Event.stop(Events.ON_POST_INIT)
    end)

    Event.register(Events.ON_POST_INIT, function()
        print("This callback will never be called.");
    end)

.. _EventCreate-anchor:

create()
--------

Creates a new unique event identifier.

**Result:**
    **number** user event id.

.. code-block:: lua

    myEventId = Event.create()

raise(eventId, data)
--------------------

Raises **all** registered events with `eventId` in **all** loaded mods.

**Parameters:**
    | **number** eventId.
    | **table** data.

.. code-block:: lua

    myEventId = Event.create()
    Event.register(myEventId, function(data) 
        print(type(data[1])) -- string
        print(type(data[2])) -- number
        print(type(data[3])) -- boolean
    end)
    Event.raise(myEventId, {"string", 12345, true})

raiseSpecified(eventId, modname, data)
--------------------------------------

Raises **all** registered events with `eventId` in the **specified** mod.

**Parameters:**
    | **number** eventId.
    | **table** data.

.. code-block:: lua

    Event.raiseSpecified(myEventId, "specifiedMod", {"string", 12345, true})

.. _CoreEvents-anchor:

----------------------------------------------------------------------------

Core events
===========

All core (provided by C++) events registered in "Events" table.

ON_POST_INIT
------------

Does not pass any arguments.
Called when all scripts are loaded. Example:

.. code-block:: lua

    Event.register(Events.ON_POST_INIT, function()
        print("Server initialized.")
    end)

ON_EXIT
-------

**Contains:**
    | ``boolean`` exit status. If ``status`` is ``true`` this means that the server closes with an error.
.. code-block:: lua

    Event.register(Events.ON_POST_INIT, function(status)
        if status == true then
            print("Server is stopped with an error.")
        else
            print("Server is closed peacefully.") 
        end
    end)

ON_PLAYER_CONNECT
-----------------

**Contains:**
    | :doc:`player<./player>` player
**Result:**
    **boolean**. Accept new player.

.. code-block:: lua

    Event.register(Events.ON_PLAYER_CONNECT, function(player)
        io.write(("Connected player %s\n"):format(player.name))
        return true
    end)

ON_PLAYER_DISCONNECT
--------------------

**Contains:**
    | :doc:`player<./player>` player

.. code-block:: lua

    Event.register(Events.ON_PLAYER_DISCONNECT, function(player)
        io.write(("Disconnected player %s\n"):format(player.name))
    end)


ON_PLAYER_DEATH
---------------

**Contains:**
    | :doc:`player<./player>` player
    | **string**              deathReason

.. code-block:: lua

    Event.register(Events.ON_PLAYER_DEATH, function(player, deathReason)
        io.write(("Player %s dead with reason %s.\n"):format(player.name, deathReason))
    end)

ON_PLAYER_RESURRECT
-------------------

**Contains:**
    | :doc:`player<./player>` player

.. code-block:: lua

    Event.register(Events.ON_PLAYER_RESURRECT, function(player)
        io.write(("Player resurrected %s.\n"):format(player.name))
    end)

ON_PLAYER_CELLCHANGE
--------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_KILLCOUNT
------------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_ATTRIBUTE
-------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_SKILL
---------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_LEVEL
---------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_BOUNTY
----------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_EQUIPMENT
-------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_INVENTORY
-------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_JOURNAL
-----------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_FACTION
-----------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_SHAPESHIFT
--------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_SPELLBOOK
-------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_TOPIC
---------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_DISPOSITION
---------------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_BOOK
--------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_MAP
-------------

**Not used.**

ON_PLAYER_REST
--------------

**Contains:**
    | :doc:`player<./player>` player

ON_PLAYER_SENDMESSAGE
---------------------

.. tip::

   This event is not recommended for parsing commands.
   Use :doc:`CommandController<./commandCotroller>` instead.

**Contains:**
    | :doc:`player<./player>` player
    | **string** message.

ON_PLAYER_ENDCHARGEN
--------------------

**Contains:**
    | :doc:`player<./player>` player

Called when player finishes the character generation sequence

.. _OnGUIAction-anchor:

ON_GUI_ACTION
-------------

**Contains:**
    | :doc:`player<./player>` player
    | **number** id
    | **string** data

.. code-block:: lua

    myMsgBoxId = 123
    Event.register(Events.ON_PLAYER_CONNECT, function(player)
        player:getGUI():customMessageBox(myMsgBoxId, "Wanna play on my cool server?", "Yep;Nope")
    end)
    
    Event.register(Events.ON_GUI_ACTION, function(player, id, data)
        if id == myMsgBoxId then
            if tonumber(data) == 0 then -- first "Yep" button
                player:message("Welcome!\n", false)
            elseif tonumber(data) == 1 then -- "Nope" button
                player:kick()
            end
        end
    end)

ON_REQUEST_PLUGIN_LIST
----------------------

**Contains:**
    | **number** id
    | **number** field
**Result:**
    | **string**.

ON_MP_REFNUM
------------

**Contains:**
    | **number** currentMpNum

ON_ACTOR_EQUIPMENT
------------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** actors. Array contains :doc:`actors<./actor>`.

ON_ACTOR_CELL_CHANGE
--------------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** actors. Array contains :doc:`actors<./actor>`.

ON_ACTOR_LIST
-------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** actors. Array contains :doc:`actors<./actor>`.

ON_ACTOR_TEST
-------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** actors. Array contains :doc:`actors<./actor>`.

ON_CELL_LOAD
------------

**Contains:**
    | :doc:`player<./player>` player
    | **string** description

ON_CELL_UNLOAD
--------------

**Contains:**
    | :doc:`player<./player>` player
    | **string** description

ON_CELL_DELETION
----------------

**Contains:**
    | **string** description

Called when ``cell`` removed from CellController

ON_CONTAINER
------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** containers. Array contains :doc:`containers<./container>`.

ON_DOOR_STATE
-------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

ON_OBJECT_PLACE
---------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

ON_OBJECT_STATE
---------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

ON_OBJECT_SPAWN
---------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

ON_OBJECT_DELETE
----------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

ON_OBJECT_LOCK
--------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

ON_OBJECT_SCALE
---------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

ON_OBJECT_TRAP
--------------

**Contains:**
    | :doc:`player<./player>` player
    | **array** objects. Array contains :doc:`objects<./object>`.

