Timer API
=========

TimerCtrl
---------

``TimerCtrl`` is a global scope table.

create(callback, msec, args)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Creates timer but not starts it.

**Parameters:**
    | **function** callback. Will be called when the timer expires
    | **number** msec.
    | **table** args. Array of arguments
**Return:**
    | **Timer** new :ref:`timer<Timer-anchor>`.

kill(timer)
^^^^^^^^^^^

Stops the timer and marks it for deletion.

.. important::
    This function only hints that the timer should be deleted. You should nonetheless set all references to a ``timer`` to ``nil`` or another type and wait for Lua\'s GC.

**Parameters:**
    | **Timer** timer.

--------------------------------------

.. _Timer-anchor:

Timer
-----

Can be created via "TimerCtrl.create".

.. code-block:: lua

    local timer
    function timerCallback(data)
        print(data[1] .. " from timer")
        TimerCtrl.kill(timer)
        timer = nil -- mark timer for GC
        collectgarbage("collect") -- forced collection of the released resources (just for testing)
    end

    timer = TimerCtrl.create(timerCallback, 2000, {"Hello", 100500})

    timer:start()

start()
^^^^^^^

stop()
^^^^^^

Marks a timer as stopped, but not deleted.

restart(msec)
^^^^^^^^^^^^^

Restarts a timer with a new target time.

**Parameters:**
    | **number** msec.

isElapsed()
^^^^^^^^^^^

**Return:**
    | **boolean** ``true`` if timer is stopped.

