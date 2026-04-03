Mirror
======

**Alias:** ``M I``

Creates a mirrored copy of selected objects about a specified line.

.. image:: ../../icons/mirror.svg
   :width: 48
   :alt: Mirror icon

----

Description
-----------

The Mirror command reflects selected objects across a mirror line defined by two points. The mirror line can be at any angle. By default, the original objects are kept; you can optionally erase them to produce a pure reflection.

Workflow
--------

**Select-first method (recommended):**

1. Select the objects you want to mirror.
2. Type ``M I`` and press ``Space`` or ``Enter``.
3. **Specify first point of mirror line:** Click the start point of the reflection axis.
4. **Specify second point of mirror line:** Click the end point of the reflection axis.
5. **Erase source objects? [Yes/No]:** Press ``Enter`` to keep the originals, or type ``Y`` and press ``Enter`` to remove them.

**Command-first method:**

1. Type ``M I`` and press ``Space`` or ``Enter``.
2. **Select objects:** Click the objects, then press ``Enter``.
3. **Specify first point of mirror line:** Click the start of the axis.
4. **Specify second point of mirror line:** Click the end of the axis.
5. **Erase source objects? [Yes/No]:** Press ``Enter`` to keep or ``Y`` to erase.

Tips
----

- To mirror about the horizontal axis, pick two points at the same Y coordinate.
- To mirror about the vertical axis, pick two points at the same X coordinate.
- Arc directions are automatically reversed so curves remain geometrically correct after mirroring.
- Type ``Y`` at the erase prompt to move objects to their mirrored position rather than creating a copy.

See Also
--------

:doc:`copy` | :doc:`move` | :doc:`rotate`
