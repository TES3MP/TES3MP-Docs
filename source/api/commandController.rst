CommandController
=================

``CommandController`` is a global scope table.

The command controller helps developers create new chat commands easily.

It intercepts chat messages that start with "/" or "!" and have a message length of at least 2. Command arguments are between quotes and are separated from each other by spaces. Any argument that is not between quotes is regarded as a one word argument.

Example:

.. code-block:: lua

    function helloCommand(player, args)
        if #args < 1 then
            return false --whoops arguments less than 1
        end
        player:message("Hello. "..args[1], false);
        return true
    end
    CommandController.registerCommand("hello", helloCommand, "sends hello + message to player")

registerCommand(command, callback, helpMessage)
-----------------------------------------------

Registers new unique ``command`` in commands list

**Parameters:**
    | **string** command. The command should be unique and not contain the command prefix symbols.
    | **function** callback. Parameters should be :doc:`player<./player>` and a **table** containing the parsed arguments. 
    | It should return ``true`` on success and will display the ``helpMessage`` on failure.
    | **string** helpMessage. Can be taken from getHelpStrings()
**Return:**
    | **boolean** ``true`` on success.

unregisterCommand(command)
--------------------------

**Parameters:**
    | **string** command. The command should be unique and not contain the command prefix symbols.

hasCommand(command)
-------------------

**Parameters:**
    | **string** command. The command should be unique and not contain the command prefix symbols.
**Return:**
    | **boolean** ``true`` if the command is registered.

getHelpStrings()
----------------

**Return:**
    | **table** array with help **string**\`s (command, helpMsg, command, HelpMsg, ...)
