Polyline
========

**Alias:** ``P L``

Creates a connected sequence of line segments as a single object.

.. image:: ../../icons/polyline.svg
   :width: 48
   :alt: Polyline icon

----

Description
-----------

The Polyline command draws a series of connected straight segments that are treated as a single entity. Unlike the Line command, all segments belong to one object and can be selected, moved, or edited together.

Workflow
--------

1. Type ``P L`` and press ``Space`` or ``Enter``.
2. **Specify start point:** Click a point on the canvas or type coordinates.
3. **Specify next point:** Click the next point or type a distance.
4. Continue specifying points to add further segments.
5. Press ``Enter`` or ``Escape`` to end the command, or type ``Close`` to join back to the start.

Options available at the *Specify next point* prompt:

- **Arc** — Switches to arc segment mode. Subsequent points are connected with arcs rather than straight lines. Available after the first segment.
- **Line** — Switches back to straight line segment mode when in arc mode. Available after the first segment.
- **Close** — Closes the polyline by connecting the last point back to the first, creating a closed shape. Available after two or more segments have been drawn.
- **Undo** — Removes the last point and returns to the previous step. Available after the first segment.

Tips
----

- Use Ortho mode (``F8``) to constrain segments to horizontal or vertical.
- A polyline can be :doc:`explode`\d into individual line segments.
- Closing a polyline by snapping back to the start point creates a filled, closed shape compatible with :doc:`hatch`.

DXF Representation
-------------------

A polyline is stored as an ``LWPOLYLINE`` (lightweight polyline) entity in the DXF :doc:`../dxf` ``BLOCKS`` section. Each vertex is stored as a pair of group codes ``10`` / ``20``.

.. code-block:: text

   0
   LWPOLYLINE
   8          ← layer name
   0
   90         ← number of vertices
   3
   70         ← flags: 0 = open, 1 = closed
   0
   10         ← vertex 1 X
   0.0
   20         ← vertex 1 Y
   0.0
   10         ← vertex 2 X
   50.0
   20         ← vertex 2 Y
   0.0
   10         ← vertex 3 X
   50.0
   20         ← vertex 3 Y
   30.0

A closed polyline has flag ``1`` set in group code ``70``, causing the last vertex to connect back to the first.

See Also
--------

:doc:`line` | :doc:`rectangle` | :doc:`explode` | :doc:`../dxf`
