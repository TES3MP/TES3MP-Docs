Global Functions
================

Global functions registered in the root (_G) Lua namespace.

getCurrentMpNum()
-----------------

**Return:**
    | **number** current mpNum.

setCurrentMpNum(mpNum)
----------------------

**Parameters:**
    | **number** mpNum. Overrides the mpNum on the server.
    
logMessage(level, message)
--------------------------

Write a log message ``with`` its own timestamp.

**Parameters:**
    | **number** level.  The logging level used. See :ref:`Log constants <LogLevelConstants-anchor>`
    | **string** message.


logAppend(level, message)
-------------------------
Write a log message ``without`` its own timestamp.

**Parameters:**
    | **number** level.  The logging level used.
    | **string** message.

stopServer(code)
----------------

**Parameters:**
    | **number** code.

banAddress(address)
-------------------

**Parameters:**
    | **string** address.

unbanAddress(address)
---------------------

**Parameters:**
    | **string** address.

setRuleValue(key, value)
------------------------

**Parameters:**
    | **string** key.
    | **string** or **number** key.

setModname(modname)
-------------------

**Parameters:**
    | **string** modname.

setHostname(hostname)
---------------------

**Parameters:**
    | **string** hostname.

setServerPassword(passw)
------------------------

**Parameters:**
    | **string** passw. if **nil**, the password will be removed.


setHour(hour)
-------------

Sets the ingame ``hour`` for each player.

**Parameters:**
    | **number** hour as a float.

setMonth(month)
---------------

Sets the ingame ``month`` for each player.

**Parameters:**
    | **number** month.

setDay(day)
-----------

Sets the ingame ``day`` of the month for each player.

**Parameters:**
    | **number** day.

getDataFolder()
---------------

**Return:**
    | **string** The data folder for current script addon.

-------------------------------------------------

Utils
=====

string:split(sep)
-----------------

Splits a string via a separator.

**Parameters:**
    | **string** or **nil** sep. if ``sep`` is **nil** then ":" delimiter is used by default
**Return**
    | **table** array of **string**\`s.
    
    
-------------------------------------------------

.. _LogLevelConstants-anchor:

Log
===
Log level constants

LOG_FATAL
---------

LOG_ERROR
---------

LOG_WARN
--------

LOG_INFO
--------

LOG_VERBOSE
-----------

LOG_TRACE
---------

