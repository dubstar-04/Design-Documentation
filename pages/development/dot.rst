Dot Product
===========

**Method:** ``point.dot(that)``

**Returns:** ``number``

----

Description
-----------

The dot product is a scalar value that measures how much two vectors point in
the same direction. Given two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}`
originating from the same point, it is defined as:

.. math::

   \mathbf{a} \cdot \mathbf{b} = a_x b_x + a_y b_y

This is equivalent to:

.. math::

   \mathbf{a} \cdot \mathbf{b} = |\mathbf{a}|\,|\mathbf{b}|\cos\theta

where :math:`\theta` is the angle between the two vectors and :math:`|\mathbf{v}|`
denotes the magnitude (length) of vector :math:`\mathbf{v}`.

Interpreting the sign
~~~~~~~~~~~~~~~~~~~~~

+---------------------+----------------------------------------------------------+
| Result              | Meaning                                                  |
+=====================+==========================================================+
| Positive            | Vectors point in the same general direction (:math:`\theta < 90°`) |
+---------------------+----------------------------------------------------------+
| Zero                | Vectors are exactly perpendicular (:math:`\theta = 90°`) |
+---------------------+----------------------------------------------------------+
| Negative            | Vectors point in opposite directions (:math:`\theta > 90°`) |
+---------------------+----------------------------------------------------------+

Scalar projection
~~~~~~~~~~~~~~~~~

Dividing the dot product by the magnitude of :math:`\mathbf{b}` gives the
*scalar projection* of :math:`\mathbf{a}` onto :math:`\mathbf{b}` — the signed
length of :math:`\mathbf{a}`'s shadow along the direction of :math:`\mathbf{b}`:

.. math::

   \text{proj} = \frac{\mathbf{a} \cdot \mathbf{b}}{|\mathbf{b}|}

Implementation
--------------

.. code-block:: javascript

   dot(that) {
     return this.x * that.x + this.y * that.y;
   }

Usage in Design
---------------

The dot product is used internally by ``perpendicular()`` to compute the
parameter :math:`t` that locates the foot of the perpendicular from a point onto
a line. It is also used wherever two direction vectors need to be compared —
for example when determining whether a snap point lies within an expected
angular range.

See Also
--------

:doc:`cross` | :doc:`perpendicular` | :doc:`../development`
