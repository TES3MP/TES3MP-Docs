.. _Factions-anchor:

Factions
========

addFaction(faction)
-------------------

**Parameters:**
    | :ref:`Faction<Faction-anchor>` faction.


changesAction
-------------

**Property**:
    | **number**. 0 - Rank, 1 - Expulsion state, 2 - Both

getFaction(idx)
---------------

**Parameters:**
    | **number** idx.
**Return:**
    | :ref:`Faction<Faction-anchor>`.

setFaction(idx, faction)
------------------------

**Parameters:**
    | **number** idx.
    | :ref:`Faction<Faction-anchor>` faction.

clear()
-------

Purges changes.


size()
------

**Return:**
    | **number** Current number of :ref:`faction<Faction-anchor>`\`s

------------------------------------------------------

.. _Faction-anchor:

Faction
=======

factionId
---------

**Property**:
    | **string**.


rank
----

**Property**:
    | **number**.

isExpelled
----------

**Property**:
    | **boolean**.

reputation
----------

**Property**:
    | **number**.

