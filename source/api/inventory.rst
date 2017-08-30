Inventory
=========

.. todo::

    Add example with player:getInventory()

getInventoryChangesSize()
-------------------------

**Return**:
    | **number**.

addItem(refId, count, charge)
-----------------------------

**Parameters:**
    | **string** refId.
    | **number** count.
    | **number** charge.

removeItem(refId, count)
------------------------

**Parameters:**
    | **string** refId.
    | **number** count.

getInventoryItem(idx)
---------------------

**Parameters:**
    | **number** idx.
**Return:**
    | **string** refId.
    | **number** count.
    | **number** charge.


equipItem(slot, refId, count, charge)
-------------------------------------

**Parameters:**
    | **number** slot.
    | **string** refId.
    | **number** count.
    | **number** charge.

unequipItem(slot)
-----------------

**Parameters:**
    | **number** slot.

hasItemEquipped(refId)
----------------------

**Parameters:**
    | **string** refId.
**Return:**
    | **boolean** ``true`` if item is equipped.

getEquipmentItem(slot)
----------------------

**Parameters:**
    | **number** slot.
**Return:**
    | **string** refId.
    | **number** count.
    | **number** charge.

