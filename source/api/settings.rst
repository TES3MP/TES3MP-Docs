Settings
========

setConsoleAllow(state)
----------------------

Enables or disables the console for a player.

**Parameters:**
    | **boolean** state.

setDifficulty(difficulty)
-------------------------

.. tip::
    The default values represent the limits of the slider used in OpenMW.
    They are neither the upper nor the lower limit.

Changes the difficulty for a player.

**Parameters:**
    | **number** difficulty. Default values from -100 to 100.

.. code-block:: lua

    if player.race == "wood elf" then
        player:getSettings():setDifficulty(500)
    end
