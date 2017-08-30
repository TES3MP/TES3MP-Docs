Spell API
=========

.. todo::
    Spell API

.. _Effect-anchor:

Effect
------

id
^^

**Property:**
    | **number**.

skill
^^^^^

**Property:**
    | **number**.

attribute
^^^^^^^^^

**Property:**
    | **number**.

range
^^^^^

**Property:**
    | **number**.

area
^^^^

**Property:**
    | **number**.

duration
^^^^^^^^

**Property:**
    | **number**.

magMin
^^^^^^

**Property:**
    | **number**.

magMax
^^^^^^

**Property:**
    | **number**.

----------------------------------

.. Spell-anchor:

Spell
-----

id
^^

**Property:**
    | **string**.

name
^^^^

**Property:**
    | **string**.

type
^^^^

**Property:**
    | **number**.

cost
^^^^

**Property:**
    | **number**.

flags
^^^^^

**Property:**
    | **number**.

getEffectCount()
^^^^^^^^^^^^^^^^

**Return:**
    | **number**.

addEffect(effect)
^^^^^^^^^^^^^^^^^

**Parameters:**
    | :ref:`Effect <Effect-anchor>` effect.

getEffect(idx)
^^^^^^^^^^^^^^

**Parameters:**
    | **number** idx.
**Return:**
    | :ref:`Effect <Effect-anchor>` effect.

---------------------------------------------------

.. Spells-anchor:

Spells
------

addCustomSpell(spell)
^^^^^^^^^^^^^^^^^^^^^
**Parameters:**
    | :ref:`Effect <Spell-anchor>` spell.

getCustomSpell(idx)
^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **number** idx.
**Return:**
    | :ref:`Effect <Spell-anchor>` spell.

addDefaultSpell(spellId)
^^^^^^^^^^^^^^^^^^^^^^^^

**Parameters:**
    | **string** spellId.

size()
^^^^^^

**Return:**
    | **number**.

