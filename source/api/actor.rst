.. _Actor-anchor:

Actor
=====

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

getFatigue(base, current)
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

.. warning::

    ``addItem``, ``removeItem``, ``getInventoryItem`` are not used by :ref:`Actor<Actor-anchor>`

**Return:**
    | :doc:`Inventory <./inventory>` inventory.

refId
-----

**Property**:
    | **string**.

refNumIndex
-----------

**Property**:
    | **number**.

mpNum
-----

**Property**:
    | **number**.

Actors
======

``Actors`` is a global scope table.

createActor()
-------------

**Return:**
    | :ref:`Actor<Actor-anchor>` new entity.

sendActors(player, actors, cellDescription, toAll)
--------------------------------------------------

**Parameters:**
    | :doc:`./player` player.
    | **table** array of :ref:`Actor<Actor-anchor>`\`s.
    | **string** cellDescription.
    | **boolean** toAll.

sendList(player, actors, cellDescription, toAll)
------------------------------------------------

**Parameters:**
    | :doc:`./player` player.
    | **table** array of :ref:`Actor<Actor-anchor>`\`s.
    | **string** cellDescription.
    | **boolean** toAll.

requestList(player, cellDescription)
------------------------------------

**Parameters:**
    | :doc:`./player` player.
    | **string** cellDescription.

getActors(player, cellDescription)
----------------------------------

**Parameters:**
    | :doc:`./player` player.
    | **string** cellDescription.

