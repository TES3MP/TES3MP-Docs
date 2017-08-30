Data global table
=================

Data table can be used for communicating between mods.

Core table
----------
Core table contains info about current version, protocol and loaded mods.

loadedMods
^^^^^^^^^^

**Property**:
    | **table**. Array with names of mods.
    
NEXT_VERSION
^^^^^^^

**Property**:
    | **string**. NEXT VERSION release date (always returns ``Soon™``).

VERSION
^^^^^^^

**Property**:
    | **string**. Current TES3MP version.

PROTOCOL
^^^^^^^^
**Property**:
    | **string**. Current TES3MP networking protocol.

