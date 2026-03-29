Development
===========

Design-Core is built on a geometry engine centred around the :code:`Point` class.
As well as representing a 2D coordinate, :code:`Point` provides a set of vector
mathematics methods used throughout the codebase — in entity construction,
snapping, trimming, dimension placement, and more.

This section documents the more advanced methods, explaining the underlying
mathematics and describing where each is used within Design.

.. toctree::
   :hidden:
   :maxdepth: 1

   development/dot
   development/cross
   development/lerp
   development/rotate
   development/project
   development/perpendicular
   development/bulge

----

Vector Methods
--------------

.. list-table::
   :widths: 20 80
   :header-rows: 1

   * - Method
     - Summary
   * - :doc:`development/dot`
     - Scalar measure of how much two vectors point in the same direction.
       Returns positive, zero, or negative based on the angle between them.
   * - :doc:`development/cross`
     - Signed area of the parallelogram formed by two vectors.
       Indicates the turn direction (clockwise or counter-clockwise) from one
       vector to another.
   * - :doc:`development/lerp`
     - Linear interpolation between two points at a fractional position
       :math:`t \in [0, 1]` along the segment.
   * - :doc:`development/rotate`
     - Rotates a point about a centre by an angle in radians using the 2D
       rotation matrix.
   * - :doc:`development/project`
     - Moves a point along a bearing (angle in radians) by a given distance.
   * - :doc:`development/perpendicular`
     - Finds the foot of the perpendicular from a point onto an infinite line
       defined by two points.
   * - :doc:`development/bulge`
     - Scalar value stored on a polyline vertex that encodes an arc segment.
       Covers the sign convention, radius formula, and centre-point derivation.
