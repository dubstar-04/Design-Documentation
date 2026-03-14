Rectangle
=========

**Alias:** ``R E C``

Creates a rectangular closed polyline from two opposite corner points.

.. image:: ../../icons/rectangle.svg
   :width: 48
   :alt: Rectangle icon

----

Description
-----------

The Rectangle command draws a closed rectangular polyline by specifying two diagonally opposite corner points. The result is a single polyline object with four segments.

Workflow
--------

1. Type ``R E C`` and press ``Space`` or ``Enter``.
2. **Specify first corner:** Click a point on the canvas or type coordinates.
3. **Specify opposite corner:** Click the diagonally opposite corner, or type dimensions relative to the first point (e.g. ``@100,50`` for a 100×50 rectangle).

Tips
----

- Use relative coordinates (``@width,height``) to create a rectangle of an exact size from the first corner.
- A rectangle is a closed polyline and can be :doc:`explode`\d into four individual line segments.
- Rectangles work well as boundary areas for :doc:`hatch`.

DXF Representation
-------------------

A rectangle is stored as a closed ``LWPOLYLINE`` entity in the DXF :doc:`../dxf` ``BLOCKS`` section — the same entity type as :doc:`polyline` but with the closed flag (group code ``70``, value ``1``) set and exactly four vertices.

.. code-block:: text

   0
   LWPOLYLINE
   8          ← layer name
   0
   90         ← number of vertices
   4
   70         ← flags: 1 = closed
   1
   10         ← corner 1 X
   0.0
   20         ← corner 1 Y
   0.0
   10         ← corner 2 X
   100.0
   20         ← corner 2 Y
   0.0
   10         ← corner 3 X
   100.0
   20         ← corner 3 Y
   50.0
   10         ← corner 4 X
   0.0
   20         ← corner 4 Y
   50.0

See Also
--------

:doc:`line` | :doc:`polyline` | :doc:`explode` | :doc:`../dxf`
