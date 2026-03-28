Fillet
======

**Alias:** ``F``

.. image:: ../../icons/fillet.svg
   :width: 48
   :alt: Fillet icon

Rounds the corner between two lines or polyline segments with an arc of a specified radius.

----

Description
-----------

The Fillet command trims or extends two lines (or adjacent polyline segments) and inserts a smooth arc tangent to both at the corner. The radius of the arc is set before selecting the objects.

When the radius is zero, Fillet behaves like a sharp trim — both lines are extended or trimmed to their intersection with no arc added.

Workflow
--------

1. Type ``F`` and press ``Space`` or ``Enter``.
2. Optionally set options before selecting objects:

   - ``Radius`` — Specify the fillet radius.
   - ``Trim`` — Choose whether the original lines are trimmed after the fillet arc is applied (``Trim`` or ``No trim``).

3. **Select first line:** Click the first line or polyline segment.
4. **Select second line:** Click the second line or adjacent polyline segment.

The fillet arc is drawn tangent to both lines and, in Trim mode, the original segments are shortened to the tangent points.

Options
-------

.. list-table::
   :header-rows: 1
   :widths: 20 80

   * - Option
     - Description
   * - ``Radius``
     - Set the fillet arc radius. A radius of ``0`` trims both lines to their sharp intersection.
   * - ``Trim``
     - Toggle trim mode. In ``Trim`` mode the lines are shortened to the arc tangent points. In ``No trim`` mode the arc is added without modifying the original lines.

Tips
----

- Setting the radius to ``0`` trims both lines to their sharp intersection with no arc added.
- The side of the line you click determines which corner is filleted when lines cross.
- Fillet works on adjacent segments of a polyline as well as on two separate lines.

See Also
--------

:doc:`chamfer` | :doc:`trim` | :doc:`extend`
