Object API
==========

.. _Container-anchor:

Container
---------

refId
^^^^^

**Property:**
    | **string**.

refNum
^^^^^^

**Property:**
    | **number**.

mpNum
^^^^^

**Property:**
    | **number**.

getItem(idx)
^^^^^^^^^^^^

**Parameters:**
    | **number** idx.
**Return:**
    | **string** refId.
    | **number** count.
    | **number** charge.

addItem(refId, count, charge)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **string** refId.
    | **number** count.
    | **number** charge.

setItem(idx, refId, count, charge)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **number** idx.
    | **string** refId.
    | **number** count.
    | **number** charge.

getActionCount(idx)
^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **number** idx.

**Return:**
    | **number** action.

---------------------------------------------------

.. _Object-anchor:

Object
------

refId
^^^^^

**Property:**
    | **string**.

refNum
^^^^^^

**Property:**
    | **number**.

mpNum
^^^^^

**Property:**
    | **number**.

getPosition()
^^^^^^^^^^^^^

**Return:**
    | **number** x.
    | **number** y.
    | **number** z.

setPosition(x, y, z)
^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **number** x.
    | **number** y.
    | **number** z.

getRotation()
^^^^^^^^^^^^^

**Return:**
    | **number** x.
    | **number** y.
    | **number** z.

setRotation(x, y, z)
^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **number** x.
    | **number** y.
    | **number** z.

count
^^^^^
**Property:**
    | **number**.

goldValue
^^^^^^^^^

**Property:**
    | **number**.

scale
^^^^^

**Property:**
    | **number**. floating point value


state
^^^^^

**Property:**
    | **boolean**.

doorState
^^^^^^^^^

**Property:**
    | **number**.

lockLevel
^^^^^^^^^

**Property:**
    | **number**.

setDisarmState(state)
^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **boolean** state.

setMasterState(state)
^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **boolean** state.

---------------------------------------------------

.. _ObjectCtrl-anchor:

ObjectCtrl
----------

``ObjectCtrl`` is a global scope table.

sendObjects(player, objects, cellDescription)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | :doc:`Player <./player>` player.
    | **table** objects. Array of :ref:`Objects <./Object-anchor>`.
    | **string** cellDescription

sendContainers(player, containers, cellDescription)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | :doc:`Player <./player>` player.
    | **table** objects. Array of :ref:`Containers <./Container-anchor>`.
    | **string** cellDescription

requestContainers(player)
-------------------------

**Parameters:**
    | :doc:`Player <./player>` player.

