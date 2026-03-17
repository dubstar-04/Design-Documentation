Commands
========

*Please note that all commands have prompts displayed on the CommandLine. If in doubt read the CommandLine.*

*SpaceBar or Enter confirms a command. SpaceBar also repeats the last command.*

.. seealso::

   :doc:`/pages/shortcuts` — Keyboard shortcuts for file, canvas, and clipboard operations.

.. toctree::
   :hidden:
   :maxdepth: 1

   commands/entities/arc
   commands/entities/block
   commands/entities/circle
   commands/entities/dimension
   commands/entities/hatch
   commands/entities/line
   commands/entities/polyline
   commands/entities/rectangle
   commands/entities/text
   commands/tools/copy
   commands/tools/distance
   commands/tools/erase
   commands/tools/explode
   commands/tools/extend
   commands/tools/identify
   commands/tools/matchprop
   commands/tools/move
   commands/tools/pan
   commands/tools/purge
   commands/tools/rotate
   commands/tools/trim
   commands/tools/zoom

----

Entities
--------

Command aliases for creating drawing entities. Enter the alias followed by ``Space`` or ``Enter``.

====================================    =================   ========================================================================================================================
Icon                                    Alias               Description
====================================    =================   ========================================================================================================================
.. image:: ../icons/arc.svg             ``A``               :doc:`commands/entities/arc` — Pick a centre point, followed by start of arc and end point.
.. image:: ../icons/block.svg           ``B``               :doc:`commands/entities/block` — Create a block definition.
.. image:: ../icons/circle.svg          ``C``               :doc:`commands/entities/circle` — Pick a centre point followed by a second point to define the radius.
.. image:: ../icons/dimension.svg       ``D I M``           :doc:`commands/entities/dimension` — Create a dimension.
.. image:: ../icons/text.svg            ``D T``             :doc:`commands/entities/text` — Pick a start point, enter height, and enter the required text string.
.. image:: ../icons/hatch.svg           ``H``               :doc:`commands/entities/hatch` — Create a hatch object.
.. image:: ../icons/line.svg            ``L``               :doc:`commands/entities/line` — Pick a start point followed by consecutive points to draw lines.
.. image:: ../icons/polyline.svg        ``P L``             :doc:`commands/entities/polyline` — Pick a start point followed by consecutive points to draw a continuous polyline.
.. image:: ../icons/rectangle.svg       ``R E C``           :doc:`commands/entities/rectangle` — Pick a start point followed by the opposite corner to draw a rectangle.
====================================    =================   ========================================================================================================================

----

Tools
-----

Command aliases for modifying and measuring objects. Enter the alias followed by ``Space`` or ``Enter``.

====================================    =================   ========================================================================================================================
Icon                                    Alias               Description
====================================    =================   ========================================================================================================================
.. image:: ../icons/copy.svg            ``C O``             :doc:`commands/tools/copy` — Copy selected objects from a base point to a destination point or distance (select first or during).
.. image:: ../icons/distance.svg        ``D I``             :doc:`commands/tools/distance` — Pick two points to measure the distance between them.
.. image:: ../icons/erase.svg           ``E`` / ``Del``     :doc:`commands/tools/erase` — Remove selected objects (select first or during).
.. image:: ../icons/extend.svg          ``E X``             :doc:`commands/tools/extend` — Select boundary edge(s) followed by object(s) to extend.
.. image:: ../icons/identify.svg        ``I D``             :doc:`commands/tools/identify` — Pick a single point to display its co-ordinates.
.. image:: ../icons/move.svg            ``M``               :doc:`commands/tools/move` — Move selected objects from a base point to a destination point or distance (select first or during).
.. image:: ../icons/matchprop.svg       ``M A``             :doc:`commands/tools/matchprop` — Apply the properties of a selected object to other objects.
.. image:: ../icons/pan.svg             ``P``               :doc:`commands/tools/pan` — Shift the view without changing orientation or magnification.
.. image:: ../icons/purge.svg           ``P U``             :doc:`commands/tools/purge` — Remove unused items such as block definitions, layers, or styles.
.. image:: ../icons/rotate.svg          ``R O``             :doc:`commands/tools/rotate` — Rotate selected objects about a base point to a defined angle (select first or during).
.. image:: ../icons/trim.svg            ``T R``             :doc:`commands/tools/trim` — Select trim boundary object(s) followed by object(s) to trim.
.. image:: ../icons/explode.svg         ``X``               :doc:`commands/tools/explode` — Break a compound object into its component objects.
.. image:: ../icons/zoom.svg            ``Z``               :doc:`commands/tools/zoom` — Change the magnification of the active view.
====================================    =================   ========================================================================================================================
