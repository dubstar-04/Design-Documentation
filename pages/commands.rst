Commands
========

*Please note that all commands have prompts displayed on the CommandLine. If in doubt read the CommandLine.*

*SpaceBar or Enter confirms a command. SpaceBar also repeats the last command.*

.. toctree::
   :hidden:
   :maxdepth: 1

   commands/arc
   commands/block
   commands/circle
   commands/copy
   commands/dimension
   commands/distance
   commands/erase
   commands/explode
   commands/extend
   commands/hatch
   commands/identify
   commands/line
   commands/matchprop
   commands/move
   commands/pan
   commands/polyline
   commands/purge
   commands/rectangle
   commands/rotate
   commands/text
   commands/trim
   commands/zoom

----

Documents
---------

Keyboard shortcuts for file and history operations.

============================    ======================================================
Shortcut                        Description
============================    ======================================================
``Ctrl+N``                      **New Design** — Create a new drawing
``Ctrl+O``                      **Open** — Open an existing drawing
``Ctrl+S``                      **Save** — Save the current drawing
``Ctrl+Shift+S``                **Save As** — Save the current drawing with a new name
``Ctrl+Z``                      **Undo** — Undo the previous action
``Ctrl+Y``                      **Redo** — Redo the previously undone action
============================    ======================================================

----

General
-------

Keyboard shortcuts for application panels and navigation.

============================    ======================================================
Shortcut                        Description
============================    ======================================================
``Ctrl+L``                      **Show Layers** — Open the layers panel
``Ctrl+1``                      **Show Properties** — Open the properties panel
``Ctrl+,``                      **Preferences** — Open the application preferences
``Ctrl+?``                      **Show Shortcuts** — Open the keyboard shortcuts overview
``F1``                          **Show Help** — Open the application documentation
``Ctrl+Q``                      **Quit** — Quit the application
============================    ======================================================

----

Canvas
------

Keyboard shortcuts for canvas display and drawing modes.

============================    ======================================================
Shortcut                        Description
============================    ======================================================
``Ctrl+G``                      **Toggle Grid** — Toggle the grid visibility
``F8``                          **Toggle Ortho Mode** — Toggle orthogonal locking
``F9``                          **Toggle Snap Mode** — Toggle object snapping
``F10``                         **Toggle Polar Mode** — Toggle polar tracking
============================    ======================================================

----

Clipboard
---------

Keyboard shortcuts for selection and clipboard operations.

============================    ======================================================
Shortcut                        Description
============================    ======================================================
``Ctrl+A``                      **Select All** — Select all entities in the drawing
``Ctrl+C``                      **Copy** — Copy to clipboard
``Ctrl+X``                      **Cut** — Cut to clipboard
``Ctrl+Shift+C``                **Copy with Base Point** — Copy to clipboard using a user-defined base point
``Ctrl+V``                      **Paste** — Paste from clipboard
============================    ======================================================

----

Entities
--------

Command aliases for creating drawing entities. Enter the alias followed by ``Space`` or ``Enter``.

====================================    =================   ========================================================================================================================
Icon                                    Alias               Description
====================================    =================   ========================================================================================================================
.. image:: ../icons/arc.svg             ``A``               :doc:`commands/arc` — Pick a centre point, followed by start of arc and end point.
                                        ``B``               :doc:`commands/block` — Create a block definition.
.. image:: ../icons/circle.svg          ``C``               :doc:`commands/circle` — Pick a centre point followed by a second point to define the radius.
.. image:: ../icons/dimension.svg       ``D I M``           :doc:`commands/dimension` — Create a dimension.
.. image:: ../icons/text.svg            ``D T``             :doc:`commands/text` — Pick a start point, enter height, and enter the required text string.
                                        ``H``               :doc:`commands/hatch` — Create a hatch object.
.. image:: ../icons/line.svg            ``L``               :doc:`commands/line` — Pick a start point followed by consecutive points to draw lines.
.. image:: ../icons/polyline.svg        ``P L``             :doc:`commands/polyline` — Pick a start point followed by consecutive points to draw a continuous polyline.
.. image:: ../icons/rectangle.svg       ``R E C``           :doc:`commands/rectangle` — Pick a start point followed by the opposite corner to draw a rectangle.
====================================    =================   ========================================================================================================================

----

Tools
-----

Command aliases for modifying and measuring objects. Enter the alias followed by ``Space`` or ``Enter``.

====================================    =================   ========================================================================================================================
Icon                                    Alias               Description
====================================    =================   ========================================================================================================================
.. image:: ../icons/copy.svg            ``C O``             :doc:`commands/copy` — Copy selected objects from a base point to a destination point or distance (select first or during).
.. image:: ../icons/distance.svg        ``D I``             :doc:`commands/distance` — Pick two points to measure the distance between them.
.. image:: ../icons/erase.svg           ``E`` / ``Del``     :doc:`commands/erase` — Remove selected objects (select first or during).
.. image:: ../icons/extend.svg          ``E X``             :doc:`commands/extend` — Select boundary edge(s) followed by object(s) to extend.
.. image:: ../icons/identify.svg        ``I D``             :doc:`commands/identify` — Pick a single point to display its co-ordinates.
.. image:: ../icons/move.svg            ``M``               :doc:`commands/move` — Move selected objects from a base point to a destination point or distance (select first or during).
                                        ``M A``             :doc:`commands/matchprop` — Apply the properties of a selected object to other objects.
                                        ``P``               :doc:`commands/pan` — Shift the view without changing orientation or magnification.
                                        ``P U``             :doc:`commands/purge` — Remove unused items such as block definitions, layers, or styles.
.. image:: ../icons/rotate.svg          ``R O``             :doc:`commands/rotate` — Rotate selected objects about a base point to a defined angle (select first or during).
.. image:: ../icons/trim.svg            ``T R``             :doc:`commands/trim` — Select trim boundary object(s) followed by object(s) to trim.
                                        ``X``               :doc:`commands/explode` — Break a compound object into its component objects.
                                        ``Z``               :doc:`commands/zoom` — Change the magnification of the active view.
====================================    =================   ========================================================================================================================
