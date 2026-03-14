Block
=====

**Alias:** ``B``

Creates a reusable block definition from selected objects.

----

Description
-----------

The Block command creates a named block definition from one or more selected objects. Once defined, a block can be inserted multiple times into the drawing as a single object reference. Blocks reduce file size and allow consistent reuse of geometry.

Workflow
--------

1. Type ``B`` and press ``Space`` or ``Enter``.
2. **Select objects:** Click the objects to include in the block, then press ``Enter`` to confirm the selection.
3. **Specify insertion point:** Click the point that will act as the block's handle when it is inserted.
4. **Enter block name:** Type a name for the block and press ``Enter``.

Tips
----

- Choose an insertion point that makes the block easy to place, such as a corner, centre point, or connection point.
- Block names must be unique within the drawing.
- Inserted blocks can be :doc:`explode`\d back into their component objects if editing is required.

DXF Representation
-------------------

Blocks involve two separate DXF structures — see :doc:`../dxf` for the overall file layout:

**Block definition** — stored in the ``BLOCKS`` section, containing the geometry:

.. code-block:: text

   0
   BLOCK
   8        ← layer name
   0
   2        ← block name
   MyBlock
   10       ← base point X
   0.0
   20       ← base point Y
   0.0
   ...
   ← entity definitions (LINE, CIRCLE, etc.) go here
   ...
   0
   ENDBLK

**Block reference (INSERT)** — stored in the ``BLOCKS`` / ``ENTITIES`` section each time the block is placed:

.. code-block:: text

   0
   INSERT
   8        ← layer name
   0
   2        ← block name to reference
   MyBlock
   10       ← insertion point X
   100.0
   20       ← insertion point Y
   75.0
   41       ← X scale factor (1.0 = no scale)
   1.0
   42       ← Y scale factor
   1.0
   50       ← rotation angle in degrees
   0.0

See Also
--------

:doc:`explode` | :doc:`../dxf`
