Chamfer
=======

**Alias:** ``C H A``

.. image:: ../../icons/chamfer.svg
   :width: 48
   :alt: Chamfer icon

Bevels the corner between two lines or polyline segments by replacing it with a straight chamfer line.

----

Description
-----------

The Chamfer command trims or extends two lines (or adjacent polyline segments) to meet at a bevelled corner. The chamfer can be defined either by two distances measured along each line from the intersection, or by a distance along the first line and an angle.

When both distances are zero, Chamfer behaves like a sharp trim — both lines are extended or trimmed to their intersection with no chamfer line added.

Workflow
--------

1. Type ``C H A`` and press ``Space`` or ``Enter``.
2. Optionally set options before selecting objects:

   - ``Distance`` — Specify the chamfer distances along the first and second lines.
   - ``Angle`` — Specify the chamfer length along the first line and the chamfer angle.
   - ``Trim`` — Choose whether the original lines are trimmed after the chamfer is applied (``Trim`` or ``No trim``).
   - ``Method`` — Switch between ``Distance`` and ``Angle`` modes.

3. **Select first line:** Click the first line or polyline segment.
4. **Select second line:** Click the second line or adjacent polyline segment.

The chamfer line is drawn between the two chamfer points and, in Trim mode, the original segments are shortened accordingly.

Options
-------

.. list-table::
   :header-rows: 1
   :widths: 20 80

   * - Option
     - Description
   * - ``Distance``
     - Set the chamfer distance along the first line (Dist1) and the second line (Dist2).
   * - ``Angle``
     - Set the chamfer length along the first line and the angle of the chamfer from that line.
   * - ``Trim``
     - Toggle trim mode. In ``Trim`` mode the lines are shortened to the chamfer points. In ``No trim`` mode the chamfer line is added without modifying the original lines.
   * - ``Method``
     - Switch between ``Distance`` mode and ``Angle`` mode.

Tips
----

- Setting both distances to ``0`` trims both lines to their sharp intersection with no chamfer line.
- The first line you select determines which end is chamfered when using Angle mode.
- Chamfer works on adjacent segments of a polyline as well as on two separate lines.

See Also
--------

:doc:`fillet` | :doc:`trim` | :doc:`extend`
