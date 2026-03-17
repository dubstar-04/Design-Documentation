Command Line
============

The command line is the primary input interface in Design. It displays the current prompt, accepts typed commands and values, and provides feedback during drawing operations.

----

Overview
--------

The command line runs along the bottom of the application. When no command is active it shows ``Command:`` and is ready to accept a command alias. Once a command is running it shows a prompt describing the expected input, for example ``Line - Pick point:``.

All commands have prompts. If you are unsure what input is expected, read the command line.

----

Entering Commands
-----------------

Type a command alias and press ``Space`` or ``Enter`` to run it. Command aliases are not case-sensitive.

.. code-block:: text

   L  →  Line
   C  →  Circle
   PL →  Polyline

A full list of aliases is available on the :doc:`/pages/commands` page.

----

Confirming and Cancelling
--------------------------

.. list-table::
   :header-rows: 1
   :widths: 25 75

   * - Key
     - Action
   * - ``Space`` or ``Enter``
     - Confirm the current input or prompt.
   * - ``Space`` (no active command)
     - Repeat the last used command.
   * - ``Escape``
     - Cancel the active command and return to the ``Command:`` prompt.
   * - ``Backspace``
     - Delete the last character of the current input.
   * - ``Delete``
     - Shortcut for the Erase command.

----

Default Values
--------------

Some prompts include a default value shown in angle brackets, for example ``Specify height <2.5>:``. If you press ``Space`` or ``Enter`` without typing a value the default is used.

----

Point Input
-----------

When a command expects a point you can either click on the canvas or type the coordinates directly into the command line.

Coordinates are entered as two numbers separated by a comma: ``x,y``.

**Absolute coordinates**

Enter the exact position in the drawing:

.. code-block:: text

   100,50    → point at X=100, Y=50

**Relative coordinates**

Prefix with ``@`` to enter a position relative to the last point entered in the current command:

.. code-block:: text

   @25,0     → 25 units to the right of the last point
   @0,10     → 10 units above the last point
   @-5,-5    → 5 units left and 5 units down from the last point

Use relative coordinates when you know a distance or offset from your previous point rather than its absolute position in the drawing.

**Explicit absolute coordinates**

Prefix with ``#`` to force absolute coordinate interpretation:

.. code-block:: text

   #100,50   → point at X=100, Y=50 (explicitly absolute)

----

Numeric Input
-------------

When a command expects a numeric value — such as a radius, height, or distance — type the number and press ``Space`` or ``Enter``:

.. code-block:: text

   Circle - Enter radius: 25
   Line - Enter length: 100.5

----

Command History
---------------

The command line keeps a history of the last ten commands used.

.. list-table::
   :header-rows: 1
   :widths: 25 75

   * - Key
     - Action
   * - ``↑`` Up arrow
     - Recall the previous command in history.
   * - ``↓`` Down arrow
     - Move forward through the history.

Pressing ``Space`` with no active command also repeats the last command without needing to retype it.

----

Tips
----

- Type just enough of an alias to be unambiguous and press ``Space`` — for example ``PL`` for Polyline or ``REC`` for Rectangle.
- Use relative coordinates (``@x,y``) when constructing geometry from known distances rather than fixed positions.
- Use the Up arrow to quickly re-run a recently used command without retyping it.

----

See Also
--------

:doc:`/pages/commands` | :doc:`/pages/shortcuts`
