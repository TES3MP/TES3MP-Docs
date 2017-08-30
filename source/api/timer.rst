Timer API
=========

TimerCtrl
---------

``TimerCtrl`` is global spaced table.

create(callback, msec, args)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Creates timer but not starts it.

**Parameters:**
    | **function** callback. Will be called when timer expires
    | **number** msec.
    | **table** args. Array of arguments
**Return:**
    | **Timer** new :ref:`timer<Timer-anchor>`.

kill(timer)
^^^^^^^^^^^

Stops the timer and marks for delete

.. important::
    This function only hints timer for deleteing. You still should set all references to ``timer`` to ``nil`` or other type and wait for Lua\'s GC.

**Parameters:**
    | **Timer** timer.

--------------------------------------

.. _Timer-anchor:

Timer
-----

Can be created by "TimerCtrl.create".

.. code-block:: lua

    local timer
    function timerCallback(data)
        print(data[1] .. " from timer")
        TimerCtrl.kill(timer)
        timer = nil -- mark timer for GC
        collectgarbage("collect") -- forced collect of the released resources (just for test)
    end

    timer = TimerCtrl.create(timerCallback, 2000, {"Hello", 100500})

    timer:start()

start()
^^^^^^^

stop()
^^^^^^

Marks timer as stopped, but not deleted.

restart(msec)
^^^^^^^^^^^^^

Restarts timer with new target time.

**Parameters:**
    | **number** msec.

isElapsed()
^^^^^^^^^^^

**Return:**
    | **bollean** ``true`` if timer is stopped.

