GUI
===

See :ref:`ON_GUI_ACTION<OnGUIAction-anchor>` with example.

messageBox(id, label)
---------------------

**Parameters:**
    | **number** id.
    | **string** label.

customMessageBox(id, label, buttons)
------------------------------------

**Parameters:**
    | **number** id.
    | **string** label.
    | **string** buttons. Split buttons by ";"

inputDialog(id, label)
----------------------

**Parameters:**
    | **number** id.
    | **string** label.

passwordDialog(id, label, note)
-------------------------------

**Parameters:**
    | **number** id.
    | **string** label.
    | **string** note.

listBox(id, label, items)
-------------------------

**Parameters:**
    | **number** id.
    | **string** label.
    | **string** items. Split items by "|"

setMapVisibility()
------------------

.. todo::

    Not implemented.

setMapVisibilityAll()
---------------------

.. todo::

    Not implemented.

createWindow(width, height, callback)
-------------------------------------

**Parameters:**
    | **number** width.
    | **number** height.
    | **function** callback. Callback with args like in :ref:`setCallback<setCallback-anchor>`

**Result:**
    :ref:`window<Window-anchor>` window. Newly created window

.. code-block:: lua

    local window = player:getGUI():createWindow(500, 500, function(_window, player, data)
        for k, v in pairs(data) do
        end
    end)

deleteWindow(window)
--------------------

**Parameters:**
    |  :ref:`window<Window-anchor>` window.

----------------------------------------------

.. _Window-anchor:

Window
======
Code sample:

.. code-block:: lua

    Event.register(Events.ON_PLAYER_CONNECT, function(player)
        local window = player:getGUI():createWindow(500, 500, function(_window, player, data)
            for k, v in pairs(data) do
                if k == "Test Button" then
                    player:message(color.White .. "Pressed button in the custom window\n", false)
                    _window:clear()
                    _window:addButton(15, 15, "Another Button")
                    _window:show()
                elseif k == "Another Button" then
                    player:message(color.White .. "Pressed another button in the custom window\n", false)
                    _window:clear()
                    _window:addButton(15, 15, "Test Button")
                    _window:show()
                elseif k == "Send" then -- default button
                    player:message(color.White .. "Pressed default \"Send\" button in the custom window\n", false)
                end
            end
        end)
        window:addButton(15, 15, "Test Button")
        window:show()
        return true
    end)

addButton(x, y, label, active)
------------------------------

**Parameters:**
    | **number** x. position X
    | **number** y. position Y
    | **string** label.
    | **bool** active. ``true`` by default


addLabel(x, y, label)
---------------------

**Parameters:**
    | **number** x. position X
    | **number** y. position Y
    | **string** label.

addEditBox(x, y, w, h, id, active)
----------------------------------

**Parameters:**
    | **number** x. position X
    | **number** y. position Y
    | **number** width.
    | **number** height.
    | **string** id. Used for callback
    | **bool** active. ``true`` by default

addPassiveListBox(x, y, w, h, id, data, active)
-----------------------------------------------

**Parameters:**
    | **number** x. position X
    | **number** y. position Y
    | **number** width.
    | **number** height.
    | **string** id. Used for callback
    | **table** data. Array with elements
    | **bool** active. ``true`` by default

addActiveListBox(x, y, w, h, id, data, active)
----------------------------------------------

Active variant of ListBox. Behaves like a list with the buttons

**Parameters:**
    | **number** x. position X
    | **number** y. position Y
    | **number** width.
    | **number** height.
    | **string** id. Used for callback
    | **table** data. Array with elements
    | **bool** active. ``true`` by default

addSlider(x, y, w, h, id, active)
------------------------------------

**Parameters:**
    | **number** x. position X
    | **number** y. position Y
    | **number** width.
    | **number** height.
    | **string** id. Used for callback
    | **bool** active. ``true`` by default

show()
------

Sends window to the client

clear()
-------

Removes all widgets from window

.. _setCallback-anchor:

setCallback(callback)
---------------------
**Callback parameters:**
    | :ref:`window<Window-anchor>`
    | :doc:`player<./player>`
    | **table**. A table is an array with IDs or labels of widgets as keys. Values are also arrays: ``value[1]`` - type of widget, ``value[2]`` - data

