Perpendicular
=============

**Method:** ``point.perpendicular(Pt1, Pt2)``

**Parameters:**

- ``Pt1`` — first point defining the line
- ``Pt2`` — second point defining the line

**Returns:** ``Point`` — the foot of the perpendicular from ``this`` onto the line

----

Description
-----------

Given a point :math:`P` (``this``) and an infinite line passing through
points :math:`A` (``Pt1``) and :math:`B` (``Pt2``), ``perpendicular`` returns
the point :math:`F` on the line that is closest to :math:`P` — the *foot of the
perpendicular* from :math:`P` to the line.

Derivation
~~~~~~~~~~

Define two vectors:

.. math::

   \overrightarrow{AB} = B - A = (B_x - A_x,\ B_y - A_y)

.. math::

   \overrightarrow{AP} = P - A = (P_x - A_x,\ P_y - A_y)

Any point on the infinite line can be written as :math:`A + t\,\overrightarrow{AB}`
for some scalar :math:`t`. The foot of the perpendicular is the value of
:math:`t` that minimises the distance from :math:`P` to the line, found by
projecting :math:`\overrightarrow{AP}` onto :math:`\overrightarrow{AB}`:

.. math::

   t = \frac{\overrightarrow{AB} \cdot \overrightarrow{AP}}{|\overrightarrow{AB}|^2}

The dot product in the numerator measures how much of :math:`\overrightarrow{AP}`
lies along :math:`\overrightarrow{AB}`; dividing by the squared magnitude
normalises this to a parameter value. The foot of the perpendicular is then:

.. math::

   F = A + t\,\overrightarrow{AB}

When :math:`t = 0`, :math:`F` coincides with :math:`A`; when :math:`t = 1`,
:math:`F` coincides with :math:`B`. Values outside :math:`[0, 1]` fall on the
line extended beyond the segment.

Implementation
--------------

.. code-block:: javascript

   perpendicular(Pt1, Pt2) {
     const APx = this.x - Pt1.x;
     const APy = this.y - Pt1.y;
     const ABx = Pt2.x - Pt1.x;
     const ABy = Pt2.y - Pt1.y;

     const magAB2 = ABx * ABx + ABy * ABy;
     const ABdotAP = ABx * APx + ABy * APy;
     const t = ABdotAP / magAB2;

     const x = Pt1.x + ABx * t;
     const y = Pt1.y + ABy * t;
     return new Point(x, y);
   }

Usage in Design
---------------

- **Object snapping** — the *nearest* snap type finds the closest point on a
  line or polyline segment to the cursor by calling ``perpendicular`` with the
  segment endpoints.
- **RotatedDimension** — after the user specifies the rotation angle, the
  measured point (``Pt14``) is projected onto the dimension line axis using
  ``perpendicular``. The direction vector for the axis is first obtained with
  ``project(angleRad, 1)``, making the two methods work in tandem:

  .. code-block:: javascript

     const dimLineDir = Pt11.project(angleRad, 1);
     const foot = Pt14.perpendicular(Pt11, dimLineDir);

- **Trim / Extend** — intersection resolution uses perpendicular projection to
  determine where an entity edge meets a boundary.

See Also
--------

:doc:`dot` | :doc:`project` | :doc:`../development`
