Copy
====

**Alias:** ``C O``

Copies selected objects to one or more new locations.

.. image:: ../../icons/copy.svg
   :width: 48
   :alt: Copy icon

----

Description
-----------

The Copy command creates one or more duplicate copies of selected objects at a specified displacement. Objects can be selected before or after starting the command. Multiple copies can be placed by continuing to pick destination points.

Workflow
--------

**Select-first method (recommended):**

1. Select the objects you want to copy.
2. Type ``C O`` and press ``Space`` or ``Enter``.
3. **Specify base point:** Click a reference point on or near the selection.
4. **Specify destination point:** Click where the copy should be placed.
5. Continue clicking to place additional copies, or press ``Enter`` to end.

**Command-first method:**

1. Type ``C O`` and press ``Space`` or ``Enter``.
2. **Select objects:** Click objects to select them, then press ``Enter``.
3. **Specify base point:** Click a reference point.
4. **Specify destination point(s):** Click each destination, then press ``Enter`` to finish.

Tips
----

- Use object snap to align copies precisely with existing geometry.
- Type a relative displacement (e.g. ``@50,0``) to copy objects at an exact offset.
- To copy to the clipboard for use across drawings, use ``Ctrl+C`` / ``Ctrl+V``.

See Also
--------

:doc:`move` | :doc:`rotate`
