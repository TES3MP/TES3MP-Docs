Player
======

getPosition()
-------------

**Return:**
    | **number** x.
    | **number** y.
    | **number** z.

setPosition(x, y, z)
--------------------

**Parameters:**
    | **number** x.
    | **number** y.
    | **number** z.

getRotation()
-------------

**Return:**
    | **number** x.
    | **number** z.

setRotation(x, z)
-----------------

**Parameters:**
    | **number** x.
    | **number** z.

getHealth()
-----------

**Return:**
    | **number** base.
    | **number** current.

setHealth(base, current)
------------------------

**Parameters:**
    | **number** base.
    | **number** current.

getMagicka()
------------

**Return:**
    | **number** base.
    | **number** current.

setMagicka(base, current)
-------------------------

**Parameters:**
    | **number** base.
    | **number** current.

getFatigue()
-------------------------

**Return:**
    | **number** base.
    | **number** current.

setFatigue(base, current)
-------------------------

**Parameters:**
    | **number** base.
    | **number** current.

getCell()
---------

**Return:**
    | :ref:`Cell <Cell-anchor>` cell.

getInventory()
--------------

**Return:**
    | :doc:`Inventory <./inventory>` inventory.

kick()
------

Kicks player from the server.

ban()
-----

Bans player on the server.

address
-------

**Property:**
    | (**read-only**) **number**.

getAvgPing()
------------

**Return:**
    **number** average ping.

message(message, toAll)
-----------------------

Sends message to a certain player or to all players.

**Parameters:**
    | **string** message.
    | **boolean** toAll.

cleanChat()
-----------

Erases chat.

pid
---

**Property:**
    | (**read-only**) **number**.

guid
----

**Property:**
    | (**read-only**) **number**.

name
----

**Property:**
    | **string**.

setCharGenStage(start, end)
---------------------------

**Parameters:**
    | **number** start.
    | **number** end.

isMale()
--------

**Return:**
    | **boolean**.

setIsMale(state)
-----------

**Parameters:**
    | **boolean** state.

level
-----

**Property:**
    | **number**.

race
----

**Property:**
    | **string**.

head
----

**Property:**
    | **string**.

hair
----

**Property:**
    | **string**.

birthsign
---------

**Property:**
    | **string**.

bounty
------

**Property:**
    | **number**.

levelProgress
-------------

**Property:**
    | **number**.

creatureModel
-------------

**Property:**
    | **string**.

isCreatureName
--------------

**Property:**
    | **boolean**.

resurrect(type)
---------------

**Parameters:**
    | **number** type. 0 - start point, 1 - imperial shrine, 2 - tribunal temple.


jail(days, ignoreTeleportation, ignoreSkillIncreases, progressText, endText)
----------------------------------------------------------------------------
This is similar to the player being jailed by a guard, but provides extra parameters for increased flexibility.

It is only sent to the player being jailed, as the other players will be informed of the jailing's actual consequences via other packets sent by the affected client.

**Parameters:**
    | **number** days. The number of days to spend jailed, where each day affects one skill point.
    | **boolean** ignoreTeleportation. Whether the player being teleported to the nearest jail marker should be overridden.
    | **boolean** ignoreSkillIncreases. Whether the player's Sneak and Security skills should be prevented from increasing as a result of the jailing, overriding default behavior.
    | **string** progressText. The text that should be displayed while jailed.
    | **string** endText. The text that should be displayed once the jailing period is over.

werewolf
--------

**Property:**
    | **boolean**.

getAttribute(id)
----------------

**Parameters:**
    | **number** id.
**Return:**
    | **number** base.
    | **number** current.

setAttribute(id, base, current)
-------------------------------

**Parameters:**
    | **number** id.
    | **number** base.
    | **number** current.

getSkill(id)
------------

**Parameters:**
    | **number** id.
**Return:**
    | **number** base.
    | **number** current.
    | **number** progress. floating point number
    | **number** increase.


setSkill(id,  base, current, progress, increase)
------------------------------------------------

**Parameters:**
    | **number** id.
    | **number** base.
    | **number** current.
    | **number** progress. floating point number
    | **number** increase.


getClass()
----------

**Return:**
    | :doc:`Class <./charClass>` class.

getSettings()
-------------

**Return:**
    | :doc:`Settings <./settings>` settings.

getBooks()
----------

**Return:**
    | :doc:`Books <./books>` books.

getGUI()
--------

**Return:**
    | :doc:`GUI <./gui>` gui.

getDialogue()
-------------

**Return:**
    | :doc:`Dialogue <./dialogue>` dialogue.

getFactions()
-------------

**Return:**
    | :ref:`Factions <Factions-anchor>` factions.

getQuests()
-----------

**Return:**
    | :ref:`Quests <Quests-anchor>` quests.


getSpells()
-----------

**Return:**
    | :ref:`Spells <Spells-anchor>` spells.

getCellState(idx)
-----------------

**Parameters:**
    | **number** idx.
**Return:**
    | :ref:`CellState <CellState-anchor>` cellState.

cellStateSize()
---------------

**Return:**
    | **number**.

addCellExplored(cellDescription)
--------------------------------

**Parameters:**
    | **string** cellDescription.

setAuthority()
--------------



