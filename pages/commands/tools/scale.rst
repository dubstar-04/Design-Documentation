Scale
=====

**Alias:** ``S C``

Enlarges or reduces selected objects by a scale factor relative to a base point.

.. image:: ../../icons/scale.svg
   :width: 48
   :alt: Scale icon

----

Description
-----------

The Scale command resizes selected objects uniformly in both X and Y relative to a specified base point. The scale factor can be entered as a number, derived from a picked point distance, or calculated using a Reference length and a new target length.

Workflow
--------

**Select-first method (recommended):**

1. Select the objects you want to scale.
2. Type ``S C`` and press ``Space`` or ``Enter``.
3. **Specify base point:** Click the point that will remain fixed during scaling.
4. **Specify scale factor [Reference]:** Enter a numeric factor (e.g. ``2`` to double, ``0.5`` to halve) or type ``R`` to use the Reference method.

**Command-first method:**

1. Type ``S C`` and press ``Space`` or ``Enter``.
2. **Select objects:** Click the objects, then press ``Enter``.
3. **Specify base point:** Click the fixed point.
4. **Specify scale factor [Reference]:** Enter a factor or ``R`` for Reference.

Reference method
^^^^^^^^^^^^^^^^

The Reference option lets you scale objects to a precise size by specifying an existing length and a new target length:

1. At the scale factor prompt, type ``R`` and press ``Enter``.
2. **Specify reference length:** Pick two points that define the current size, or type the known length.
3. **Specify new length:** Pick a point to set the new size, or type the target length.

The command calculates the factor automatically as *new length ÷ reference length*.

Tips
----

- A factor greater than ``1`` enlarges objects; a factor less than ``1`` reduces them.
- Choose the base point carefully — objects are scaled away from it, so picking a corner, centre, or endpoint gives predictable results.
- Use the Reference method when you know the desired final size but not the exact scale factor.
- Scale operates in-place, modifying the selected objects directly, unlike :doc:`copy`.

See Also
--------

:doc:`move` | :doc:`rotate` | :doc:`copy`
