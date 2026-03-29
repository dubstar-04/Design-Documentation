Linear Interpolation (lerp)
===========================

**Method:** ``point.lerp(that, t)``

**Parameters:**

- ``that`` — the end point
- ``t`` — a number in the range :math:`[0, 1]`

**Returns:** ``Point``

----

Description
-----------

Linear interpolation (lerp) finds the point that lies a fractional distance
:math:`t` of the way from ``this`` to ``that`` along the straight line
between them:

.. math::

   P(t) = A + t\,(B - A) = (1 - t)\,A + t\,B

where :math:`A` is ``this`` and :math:`B` is ``that``.

Evaluating the formula at the boundary values and midpoint:

+-------+---------------------------------------------+
| t     | Result                                      |
+=======+=============================================+
| 0     | :math:`A` — the start point                 |
+-------+---------------------------------------------+
| 0.5   | Midpoint between :math:`A` and :math:`B`    |
+-------+---------------------------------------------+
| 1     | :math:`B` — the end point                   |
+-------+---------------------------------------------+

Values of :math:`t` outside :math:`[0, 1]` extrapolate beyond the segment.

Relationship to midPoint
~~~~~~~~~~~~~~~~~~~~~~~~

The built-in ``midPoint()`` method is a special case of lerp with :math:`t = 0.5`:

.. math::

   \text{midPoint}(A, B) = A.\text{lerp}(B,\ 0.5)

Implementation
--------------

.. code-block:: javascript

   lerp(that, t) {
     return new Point(
       this.x + (that.x - this.x) * t,
       this.y + (that.y - this.y) * t,
     );
   }

Usage in Design
---------------

``lerp`` is used whenever a point at a known fraction along a segment is needed
— for example, generating intermediate sample points along a line or polyline
segment for snap calculations, or computing a position part-way between two
geometry points during drawing operations.

See Also
--------

:doc:`project` | :doc:`../development`
