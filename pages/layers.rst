Layers
======

Layers are a fundamental organisational tool in CAD drawings. They allow you to group related entities together and control their appearance and visibility independently.

----

Overview
--------

Every entity in a drawing belongs to a layer. A layer has a **name**, a **colour**, a **line type**, and a **visibility state**. By assigning entities to different layers you can:

- Show or hide groups of related objects without deleting them.
- Apply consistent colours and line types across a group of entities.
- Control which parts of a drawing are visible or printed.

A drawing always has at least one layer: **Layer 0**, which is the default layer and cannot be deleted.

----

Layer Properties
----------------

.. list-table::
   :header-rows: 1
   :widths: 20 80

   * - Property
     - Description
   * - **Name**
     - A unique identifier for the layer. Names should be descriptive, for example ``Walls``, ``Dimensions``, or ``Annotations``.
   * - **Colour**
     - The default colour applied to all entities on the layer. Individual entities can override this with their own colour.
   * - **Line Type**
     - The default line type for entities on the layer, for example continuous, dashed, or centre.
   * - **Visible**
     - Controls whether entities on the layer are displayed on the canvas.
   * - **Current**
     - The active layer. All newly created entities are placed on the current layer.

----

Managing Layers
---------------

Open the Layers panel using the keyboard shortcut ``Ctrl+L`` or via the Side Kick panel.

**Creating a layer**

1. Open the Layers panel.
2. Click the **+** button.
3. A new layer is created with a default name. Edit the name in the detail panel below.

**Setting the current layer**

Select a layer in the list and click the **Set Current** button, or double-click the layer. All new entities will be drawn on this layer.

**Deleting a layer**

Select the layer and click the **−** button. A layer cannot be deleted if it is the current layer or if it contains entities.

----

Layer 0
-------

**Layer 0** is a special built-in layer that is present in every drawing. It cannot be renamed or deleted. It is primarily used as the default layer for block geometry — entities on Layer 0 inside a block definition inherit the colour and line type of the layer the block is inserted on.

----

Defpoints
---------

**Defpoints** is a special layer that is created automatically when a dimension is added to a drawing. Dimension definition points — the small points that mark the measured locations on an entity — are placed on this layer by the dimensioning system.

The Defpoints layer has one unique behaviour: entities on it are **not printed or exported**, even when the layer is visible. This means definition points appear on screen as a drawing aid but do not appear in any output.

The Defpoints layer should not be used for general drawing geometry as it will not appear in printed or exported output.

----

Tips
----

- Use clear, consistent naming conventions across drawings so layers are predictable — for example, prefix layers by discipline: ``A-Walls``, ``S-Columns``.
- Turn off layers you are not currently editing to reduce visual clutter without losing the geometry.
- Assign a distinct colour to each layer to make it easy to identify which layer an entity belongs to at a glance.

----

See Also
--------

:doc:`/pages/shortcuts` | :doc:`/pages/dxf`
