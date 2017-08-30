CommandCotroller
=================

``CommandCotroller`` is global spaced table.

Command controller aims to help developers to create new chat commands.


Command controller checks if the chat message contains "/" or "!" as a first symbol and has length of message at least 2.
It also parse arguments delimited by space symbol if you do not want to parse spaces as delimiter, you can use quotation marks in the chat to mark the argument as a string.

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

Registeres new unique ``command`` in commands list

**Parameters:**
    | **string** command. Command should be unique and does not contain command prefix.
    | **function** callback. Parameters should be :doc:`player<./player>` and **table** with parsed arguments. 
    | And should return ``true`` on success otherwise will be shown ``helpMessage``.
    | **string** helpMessage. Can be taken from getHelpStrings()
**Return:**
    | **boolean** ``true`` on success.

unregisterCommand(command)
--------------------------

**Parameters:**
    | **string** command. Command should be unique and does not contain command prefix.

hasCommand(command)
-------------------

**Parameters:**
    | **string** command. Command should be unique and does not contain command prefix.
**Return:**
    | **boolean** ``true`` if the command is registered.

getHelpStrings()
----------------

**Return:**
    | **table** array with help **string**\`s (command, helpMsg, command, HelpMsg, ...)
