Cross Product
=============

**Method:** ``point.cross(that)``

**Returns:** ``number``

----

Description
-----------

In 2D, the cross product of two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}`
is a scalar (the :math:`z`-component of the 3D cross product with the vectors
embedded in the :math:`xy`-plane):

.. math::

   \mathbf{a} \times \mathbf{b} = a_x b_y - a_y b_x

This is equivalent to:

.. math::

   \mathbf{a} \times \mathbf{b} = |\mathbf{a}|\,|\mathbf{b}|\sin\theta

where :math:`\theta` is the signed angle measured *counter-clockwise* from
:math:`\mathbf{a}` to :math:`\mathbf{b}`.

The magnitude equals the area of the parallelogram formed by the two vectors,
and equivalently twice the area of the triangle they enclose.

Interpreting the sign
~~~~~~~~~~~~~~~~~~~~~

+---------------------+----------------------------------------------------------+
| Result              | Meaning                                                  |
+=====================+==========================================================+
| Positive            | :math:`\mathbf{b}` is counter-clockwise from :math:`\mathbf{a}` |
+---------------------+----------------------------------------------------------+
| Zero                | Vectors are parallel (or one has zero length)            |
+---------------------+----------------------------------------------------------+
| Negative            | :math:`\mathbf{b}` is clockwise from :math:`\mathbf{a}` |
+---------------------+----------------------------------------------------------+

Turn direction test
~~~~~~~~~~~~~~~~~~~

Given three points :math:`A`, :math:`B`, :math:`C`, the cross product of
:math:`\overrightarrow{AB}` and :math:`\overrightarrow{AC}` tells you the
winding order:

.. math::

   \overrightarrow{AB} \times \overrightarrow{AC} =
   (B_x - A_x)(C_y - A_y) - (B_y - A_y)(C_x - A_x)

- **Positive** — :math:`A \to B \to C` turns left (counter-clockwise)
- **Zero** — the three points are collinear
- **Negative** — :math:`A \to B \to C` turns right (clockwise)

Implementation
--------------

.. code-block:: javascript

   cross(that) {
     return this.x * that.y - this.y * that.x;
   }

Usage in Design
---------------

The cross product is used to determine arc sweep direction (clockwise vs
counter-clockwise) and to test the winding order of geometry — for example,
when deciding which side of a line a point lies on, or when resolving arc
direction during polyline arc-segment creation.

See Also
--------

:doc:`dot` | :doc:`../development`
