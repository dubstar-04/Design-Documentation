Circle
======

**Alias:** ``C``

Creates a circle from a centre point and radius.

.. image:: ../../icons/circle.svg
   :width: 48
   :alt: Circle icon

----

Description
-----------

The Circle command creates a circle defined by a centre point and a radius. The radius can be specified by picking a second point on the canvas or by typing a numeric value.

Workflow
--------

1. Type ``C`` and press ``Space`` or ``Enter``.
2. **Specify centre point:** Click a point on the canvas or type coordinates.
3. **Specify radius:** Click a point to define the radius, or type a numeric value and press ``Enter``.

Tips
----

- Use object snap to place the centre point precisely on existing geometry (e.g. snapping to the midpoint of a line).
- Type the radius value directly (e.g. ``25``) for an exact circle size.
- Circles can be used as boundary edges for :doc:`trim` and :doc:`extend`.

DXF Representation
-------------------

A circle is stored as a ``CIRCLE`` entity in the DXF :doc:`../dxf` ``BLOCKS`` section.

.. code-block:: text

   0
   CIRCLE
   8       ← layer name
   0
   10      ← centre X
   50.0
   20      ← centre Y
   50.0
   40      ← radius
   25.0

See Also
--------

:doc:`arc` | :doc:`trim` | :doc:`../dxf`
