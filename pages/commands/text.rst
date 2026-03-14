Text
====

**Alias:** ``D T``

Creates a single line of text.

.. image:: ../../icons/text.svg
   :width: 48
   :alt: Text icon

----

Description
-----------

The Text command places a single line of text on the drawing. You define the insertion point, height, and the text string. The text style (font, appearance) is controlled by the current text style.

Workflow
--------

1. Type ``D T`` and press ``Space`` or ``Enter``.
2. **Specify start point:** Click where the text should begin.
3. **Specify height:** Type the text height value and press ``Enter``.
4. **Enter text:** Type the text string and press ``Enter`` to place it.

Tips
----

- Text height is in drawing units; use a value proportional to your drawing scale.
- The text is placed horizontally from the specified start point.
- To edit existing text, select it and use the Properties panel (``Ctrl+1``).

DXF Representation
-------------------

A single-line text object is stored as a ``TEXT`` entity in the DXF :doc:`../dxf` ``BLOCKS`` section.

.. code-block:: text

   0
   TEXT
   8       ← layer name
   0
   10      ← insertion point X
   10.0
   20      ← insertion point Y
   20.0
   40      ← text height
   5.0
   1       ← text string content
   Hello World
   50      ← rotation angle in degrees (0 = horizontal)
   0.0
   7       ← text style name
   Standard

See Also
--------

:doc:`../dimensions` | :doc:`../dxf`
