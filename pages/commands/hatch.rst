Hatch
=====

**Alias:** ``H``

Fills an enclosed area with a repeating pattern.

.. image:: ../../icons/hatch.svg
   :width: 48
   :alt: Hatch icon

----

Description
-----------

The Hatch command fills an enclosed boundary with a hatch pattern. The boundary must be a closed area formed by existing objects. Pick a point inside the area to detect the boundary automatically.

Workflow
--------

1. Type ``H`` and press ``Space`` or ``Enter``.
2. **Pick internal point:** Click a point inside the closed area you want to hatch.
3. The boundary is detected automatically and the area is filled with the current hatch pattern.

.. note::
   The area must be fully enclosed. If the boundary has gaps, the hatch may fail or flood outside the intended area.

Tips
----

- Ensure the boundary is fully closed before running the Hatch command.
- Use :doc:`rectangle` or closed :doc:`polyline` objects for reliable hatch boundaries.
- The hatch pattern and scale can be changed via the Properties panel (``Ctrl+1``) after placing the hatch.

DXF Representation
-------------------

A hatch is stored as a ``HATCH`` entity in the DXF :doc:`../dxf` ``BLOCKS`` section. The entity records the boundary path, fill type, and pattern definition.

.. code-block:: text

   0
   HATCH
   8        ← layer name
   0
   10       ← elevation point X (always 0 for 2D)
   0.0
   20       ← elevation point Y (always 0 for 2D)
   0.0
   2        ← pattern name (e.g. ANSI31, SOLID)
   ANSI31
   70       ← solid fill flag: 1 = solid, 0 = pattern
   0
   71       ← associativity flag: 1 = associative
   0
   91       ← number of boundary paths
   1
   ...

The boundary path section that follows records the edges (lines, arcs, polylines) that form the hatch boundary.

See Also
--------

:doc:`rectangle` | :doc:`polyline` | :doc:`../dxf`
