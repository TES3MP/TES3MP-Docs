Constants
=========

Constants is a collection (namespace) of static functions.

getAttributeCount()
-------------------

**Return:**
    | **number** the number of valid atttributes.


getSkillCount()
---------------

**Return:**
    | **number** the number of valid skills.


getAttributeId(name)
--------------------

**Parameters:**
    | **string** name. Name of attribute (case insensitive).
**Return:**
    | **number** attribute id or -1 if the attribute is not found.

.. code-block:: lua

    local luckId = Constants.getAttributeId("luck") -- luckId == 7

getSkillId(name)
----------------

**Parameters:**
    | **string** name. Name of skill (case insensitive).
**Return:**
    | **number** skill id or -1 if the skill is not found.

getAttributeName(attributeId)
-----------------------------

**Parameters:**
    | **number** attributeId. 
**Return:**
    | **string** attribute name or ``"invalid"`` if the attributeId is not found.

getSkillName(skillId)
---------------------

**Parameters:**
    | **number** skillId. 
**Return:**
    | **string** skill name or ``"invalid"`` if the skillId is not found.

getEquipmentSize()
------------------

**Return:**
    | **number** the number of slots in equipment.


