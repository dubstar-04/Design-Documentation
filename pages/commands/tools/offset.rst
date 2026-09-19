Offset
======

**Alias:** ``O``

.. image:: ../../icons/offset.svg
   :width: 48
   :alt: Offset icon

Creates a parallel copy of a line, arc, circle, or polyline at a specified distance.

----

Description
-----------

The Offset command creates a new object parallel to an existing line, arc, circle, or polyline, either at a specified distance or through a chosen point. The side to offset towards is determined by where you click relative to the selected object.

Workflow
--------

1. Type ``O`` and press ``Space`` or ``Enter``.
2. **Specify offset distance:** Enter a distance, or type ``Through`` to offset via a picked point instead.
3. **Select object:** Click the line, arc, circle, or polyline to offset.
4. **Specify point on side to offset** *(distance mode)*, or **specify through point** *(through mode)*: Click the side of the object the new copy should appear on.
5. Continue selecting objects and picking side/through points to offset further objects, or press ``Enter``/``Esc`` to end.

Options
-------

.. list-table::
   :header-rows: 1
   :widths: 20 80

   * - Option
     - Description
   * - ``Through``
     - Offset the selected object so the new copy passes through a picked point, instead of a fixed distance.

Tips
----

- The last offset distance is remembered and offered as the default the next time the command is used.
- The point you click determines which side of the object the offset copy is placed on.
- Offsetting a closed polyline or circle produces a similarly closed, uniformly scaled copy.

See Also
--------

:doc:`copy` | :doc:`mirror`
