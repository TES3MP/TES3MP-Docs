Quest API
=========

.. _JournalItem-anchor:

JournalItem
-----------

quest
^^^^^

**Property**:
    | **string**.

index
^^^^^

**Property**:
    | **number**.

actorRefId
^^^^^^^^^^

**Property**:
    | **string**.

type
^^^^

**Property**:
    | **number**.


.. _Quests-anchor:

Quests
------

getJournalChangesSize()
^^^^^^^^^^^^^^^^^^^^^^^

**Return:**
    | **number** Current number of :ref:`faction<JournalItem-anchor>`\`s

getKillChangesSize()
^^^^^^^^^^^^^^^^^^^^

**Return:**
    | **number**.

addJournalItem(journalItem)
^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | :ref:`JournalItem <JournalItem-anchor>` journalItem.

setJournalItem(idx, journalItem)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **number** idx.
    | :ref:`JournalItem <JournalItem-anchor>` journalItem.

getJournalItem(idx)
^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **number** idx.
**Return:**
    | :ref:`JournalItem <JournalItem-anchor>` journalItem.

addKill(refId, num)
^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **string** refId.
    | **number** num. Number of kills.

getKill(idx)
^^^^^^^^^^^^

**Return:**
    | **string** refId.
    | **number** number of kills.


