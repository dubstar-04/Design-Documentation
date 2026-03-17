Trim
====

**Alias:** ``T R``

Trims objects at the intersection with a selected cutting edge.

.. image:: ../../icons/trim.svg
   :width: 48
   :alt: Trim icon

----

Description
-----------

The Trim command shortens objects by cutting them at their intersection with one or more boundary (cutting) edges. First select the cutting edges, then pick the portions of objects you want to remove.

Workflow
--------

1. Type ``T R`` and press ``Space`` or ``Enter``.
2. **Select cutting edges:** Click the objects that will act as the cutting boundary, then press ``Enter``.
3. **Select objects to trim:** Click the portion of each object you want to remove (the side to cut off).
4. Continue clicking objects to trim, then press ``Enter`` or ``Escape`` to end.

Tips
----

- The part of the object you click is the part that is removed.
- If no intersection is found, the object will not be trimmed.
- Use :doc:`extend` to lengthen objects to a boundary edge instead of cutting.

See Also
--------

:doc:`extend` | :doc:`erase`
