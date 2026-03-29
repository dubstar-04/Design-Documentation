Bulge
=====

----

Description
-----------

A **bulge** value is a compact scalar attached to a polyline vertex that encodes
an arc segment between that vertex and the next. When the bulge is zero the
segment is a straight line; any non-zero value turns the segment into a circular
arc.

Bulge is defined as the tangent of one quarter of the arc's included angle
:math:`\theta`:

.. math::

   b = \tan\!\left(\frac{\theta}{4}\right)

or equivalently, the included angle is recovered from the bulge with:

.. math::

   \theta = 4\,\arctan(b)

This is implemented in the codebase as:

.. code-block:: javascript

   bulgeAngle() {
     return Math.atan(this.bulge) * 4;
   }

Sign convention
~~~~~~~~~~~~~~~

The sign of the bulge determines the sweep direction of the arc:

+---------------+----------------------------------------------+
| Bulge value   | Meaning                                      |
+===============+==============================================+
| 0             | Straight line segment                        |
+---------------+----------------------------------------------+
| Positive      | Arc sweeps **counter-clockwise** (CCW)       |
+---------------+----------------------------------------------+
| Negative      | Arc sweeps **clockwise** (CW)                |
+---------------+----------------------------------------------+

Special values
~~~~~~~~~~~~~~

+---------------------------+-----------------------------------------------+
| Bulge                     | Arc                                           |
+===========================+===============================================+
| :math:`|b| < 1`           | Arc spanning less than a semicircle           |
+---------------------------+-----------------------------------------------+
| :math:`|b| = 1`           | Exact semicircle (:math:`\theta = \pi`)       |
+---------------------------+-----------------------------------------------+
| :math:`|b| > 1`           | Arc spanning more than a semicircle           |
+---------------------------+-----------------------------------------------+

DXF Representation
------------------

In the DXF format, the bulge is stored as **group code 42** on the start vertex
of each arc segment in an ``LWPOLYLINE`` entity. A value of zero (the default)
means a straight segment and is often omitted.

.. code-block:: text

   0
   LWPOLYLINE
   8        ← layer name
   0
   90       ← vertex count
   3
   10       ← vertex 1 X
   0.0
   20       ← vertex 1 Y
   0.0
   42       ← bulge at vertex 1 (arc to vertex 2)
   1.0
   10       ← vertex 2 X
   50.0
   20       ← vertex 2 Y
   0.0

----

Calculating the Radius
----------------------

Given the start point :math:`S` (``this``) and end point :math:`E`
(``nextPoint``), the chord length is:

.. math::

   d = |SE| = \sqrt{(E_x - S_x)^2 + (E_y - S_y)^2}

The arc radius follows directly from the bulge and chord length:

.. math::

   r = \frac{d\,(1 + b^2)}{4\,|b|}

This is derived by noting that the sagitta (the perpendicular distance from the
chord midpoint to the arc) is :math:`s = |b| \cdot d / 2`, and applying the
chord–sagitta–radius relationship :math:`r = d^2 / (8s) + s / 2`.

.. code-block:: javascript

   bulgeRadius(nextPoint) {
     if (this.bulge == 0) return 0;
     return this.distance(nextPoint) * (1 + Math.pow(this.bulge, 2))
            / (4 * Math.abs(this.bulge));
   }

----

Calculating the Centre Point
-----------------------------

Finding the arc centre requires three steps.

**Step 1 — Find the apothem**

The *apothem* is the perpendicular distance from the chord midpoint to the arc
centre:

.. math::

   a = \sqrt{r^2 - \left(\tfrac{d}{2}\right)^2}

For arcs spanning more than a semicircle (:math:`|\theta| > \pi`), the centre
lies on the opposite side of the chord, so the sign is flipped:

.. math::

   a = -\sqrt{r^2 - \left(\tfrac{d}{2}\right)^2} \quad \text{when } |\theta| > \pi

.. code-block:: javascript

   apothem(nextPoint) {
     if (this.bulge == 0) return 0;
     return Math.sqrt(
       Math.pow(this.bulgeRadius(nextPoint), 2)
       - Math.pow(this.distance(nextPoint) / 2, 2)
     );
   }

**Step 2 — Find the perpendicular direction**

The centre always lies on the perpendicular bisector of the chord. The
direction from the chord midpoint to the centre is:

.. math::

   \alpha = \angle(S, E) + \frac{\pi}{2} \cdot \operatorname{sign}(b)

A positive bulge (CCW arc) places the centre to the left of the chord; a
negative bulge (CW arc) places it to the right.

**Step 3 — Project from the midpoint**

The centre is the apothem distance from the chord midpoint in direction
:math:`\alpha`:

.. math::

   C = M + a \cdot (\cos\alpha,\ \sin\alpha)

where :math:`M` is the midpoint of :math:`SE`.

.. code-block:: javascript

   bulgeCentrePoint(nextPoint) {
     const midp = this.midPoint(nextPoint);
     if (this.bulge == 0) return midp;

     let a = this.apothem(nextPoint);
     if (Math.abs(this.bulgeAngle()) > Math.PI) a = -a;

     const direction = this.angle(nextPoint)
                       + (Math.PI / 2) * Math.sign(this.bulge);
     return midp.project(direction, a);
   }

----

Computing Bulge from Geometry
------------------------------

When the user draws an arc segment in polyline mode, the bulge value is
computed from the tangent continuity condition: the new arc must start tangent
to the previous segment.

The angle delta between the incoming tangent direction and the direction from
the current point to the selected endpoint is half the included angle
:math:`\theta`:

.. math::

   b = \tan\!\left(\frac{\Delta\alpha \cdot 2}{4}\right) = \tan\!\left(\frac{\Delta\alpha}{2}\right)

In the code this is resolved via:

.. code-block:: javascript

   getBulgeFromSegment(point) {
     // ... compute lastSegAngle (tangent of prior segment at the join point)
     const mouseAngle = this.points.at(-1).angle(point) % (2 * Math.PI);
     const angleDelta = ((mouseAngle - lastSegAngle) + 3 * Math.PI)
                        % (2 * Math.PI) - Math.PI;
     // angleDelta is half the included angle
     const bulge = Math.tan((angleDelta * 2) / 4);
     return bulge;
   }

----

Usage in Design
---------------

- **Polyline drawing** — when the user switches to ``Arc`` mode, each new point
  computes a bulge value via ``getBulgeFromSegment`` so that the arc joins the
  previous segment tangentially.
- **Rendering** — ``buildDrawPoints`` in ``BasePolyline`` reads the bulge of
  each vertex: a zero bulge draws a straight line; a non-zero bulge calls
  ``bulgeCentrePoint`` and ``bulgeRadius`` to reconstruct the arc for
  drawing.
- **Snapping** — the centre snap for a polyline arc segment is found with
  ``bulgeCentrePoint``; mid-arc snaps step along the arc using the arc angle
  derived from the bulge.
- **DXF I/O** — the bulge is written as group code 42 and read back on load,
  fully preserving arc geometry across file save/open cycles.
- **Trim / Split** — ``partialBulge`` recomputes the bulge for the portion of
  an arc segment either side of a trim or split point, allowing arcs to be
  shortened without losing their curvature.

See Also
--------

:doc:`../commands/entities/polyline` | :doc:`project` | :doc:`../development`
