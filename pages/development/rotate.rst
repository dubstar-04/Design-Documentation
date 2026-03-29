Rotate
======

**Method:** ``point.rotate(centre, angle)``

**Parameters:**

- ``centre`` — the centre of rotation as a ``Point``
- ``angle`` — the rotation angle in **radians** (positive = counter-clockwise)

**Returns:** ``Point``

----

Description
-----------

Rotating a point :math:`P` about a centre :math:`C` by angle :math:`\theta`
is performed in three steps:

1. Translate :math:`P` so that :math:`C` is at the origin: :math:`P' = P - C`
2. Apply the 2D rotation matrix:

.. math::

   R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}

3. Translate back: add :math:`C` to the result.

Written out component-wise:

.. math::

   x' = C_x + (P_x - C_x)\cos\theta - (P_y - C_y)\sin\theta

.. math::

   y' = C_y + (P_x - C_x)\sin\theta + (P_y - C_y)\cos\theta

Sign convention
~~~~~~~~~~~~~~~

Following the standard mathematical convention, positive angles rotate
**counter-clockwise**. To rotate clockwise, pass a negative angle.

A full revolution is :math:`2\pi` radians (:math:`360°`). Common conversions:

+----------+-------------------------------+
| Degrees  | Radians                       |
+==========+===============================+
| 90°      | :math:`\pi / 2 \approx 1.571` |
+----------+-------------------------------+
| 180°     | :math:`\pi \approx 3.14159`   |
+----------+-------------------------------+
| 270°     | :math:`3\pi / 2`              |
+----------+-------------------------------+
| 360°     | :math:`2\pi`                  |
+----------+-------------------------------+

Implementation
--------------

.. code-block:: javascript

   rotate(centre, angle) {
     const x = centre.x + (this.x - centre.x) * Math.cos(angle)
                        - (this.y - centre.y) * Math.sin(angle);
     const y = centre.y + (this.x - centre.x) * Math.sin(angle)
                        + (this.y - centre.y) * Math.cos(angle);
     return new Point(x, y, this.bulge, this.sequence);
   }

Usage in Design
---------------

``rotate`` underpins the **Rotate** command, where every point of each selected
entity is rotated about the user-specified base point by the given angle.

It is also used internally when generating arc geometry — for example, rotating
a point around an arc centre to step through arc vertices — and in the
AngularDimension to position arrow-head endpoints around a shared intersection
point.

See Also
--------

:doc:`project` | :doc:`../development`
