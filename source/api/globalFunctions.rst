Global Functions
================

Global functions registered in root (_G) lua namespace.

getCurrentMpNum()
-----------------

**Return:**
    | **number** current mpNum.

setCurrentMpNum(mpNum)
--------------------

**Parameters:**
    | **number** mpNum. override mpNum on the serever.
    
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
    | **string** passw. if **nil**, password will be removed.


setHour(hour)
-------------

Sets ``hour`` for each player.

**Parameters:**
    | **number** hour. In float format.

setMonth(month)
---------------

Sets ``month`` for each player.

**Parameters:**
    | **number** month.

setDay(day)
-----------

Sets ``day`` for each player.

**Parameters:**
    | **number** day.

getDataFolder()
---------------

**Return:**
    | **string** data folder for current mod.

-------------------------------------------------

Utils
=====

string:split(sep)
-----------------

Splitting string by separators.

**Parameters:**
    | **string** or **nil** sep. if ``sep`` is **nil** then ":" delimiter is used by default
**Return**
    | **table** array of **string**\`s.
    
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

