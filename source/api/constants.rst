Constants
=========

Constants is collection (namespace) of static functions.

getAttributeCount()
-------------------

**Return:**
    | **number** last id of atttributes.


getSkillCount()
---------------

**Return:**
    | **number** last id of skills.


getAttributeId(name)
--------------------

**Parameters:**
    | **string** name. Name of attribute (case insensetive).
**Return:**
    | **number** attribute id or -1 if attribute not found.

.. code-block:: lua

    local luckId = Constants.getAttributeId("luck") -- luckId == 7

getSkillId(name)
----------------

**Parameters:**
    | **string** name. Name of skill (case insensetive).
**Return:**
    | **number** skill id or -1 if skill not found.

getAttributeName(attributeId)
-----------------------------

**Parameters:**
    | **number** attributeId. 
**Return:**
    | **string** attribute name or ``"invalid"`` if attributeId not found.

getSkillName(skillId)
---------------------

**Parameters:**
    | **number** skillId. 
**Return:**
    | **string** skill name or ``"invalid"`` if skillId not found.

getEquipmentSize()
------------------

**Return:**
    | **number** last slot of equipment.


