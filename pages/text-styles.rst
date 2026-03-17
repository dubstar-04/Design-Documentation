Text Styles
===========

Text styles define the appearance of text in a drawing. A style stores font, height, and formatting properties that can be applied consistently across all text entities that reference it.

----

Overview
--------

Every text entity in a drawing references a text style. The style controls the default font and appearance of the text. Using named styles ensures that text is consistent across a drawing and can be updated globally by editing the style rather than each entity individually.

A drawing always has at least one text style: **Standard**, which is the default and cannot be deleted.

----

Text Style Properties
---------------------

.. list-table::
   :header-rows: 1
   :widths: 20 80

   * - Property
     - Description
   * - **Name**
     - A unique identifier for the style. Names should reflect the intended use, for example ``Annotations``, ``Titles``, or ``Dimensions``.
   * - **Font**
     - The typeface used to render the text.
   * - **Height**
     - The default text height. If set to ``0``, the height is specified each time a text entity is created.
   * - **Backwards**
     - Mirrors the text horizontally so it reads right to left.
   * - **Upside Down**
     - Mirrors the text vertically.

----

Managing Text Styles
--------------------

Open the Text Styles panel via the Side Kick panel.

**Creating a style**

1. Open the Text Styles panel.
2. Click the **+** button.
3. A new style is created with a default name. Edit its properties in the detail panel below.

**Setting the current style**

Select a style in the list and click the **Set Current** button. All new text entities will use this style.

**Deleting a style**

Select the style and click the **−** button. A style cannot be deleted if it is the current style or if it is referenced by text entities in the drawing.

----

Standard Style
--------------

**Standard** is the built-in default text style present in every drawing. It cannot be deleted. If no other styles have been created, all text entities use Standard.

----

Tips
----

- Set the height to ``0`` in the style definition if you want to be prompted for a height each time you place text. Set a fixed height if all text of that style should be the same size.
- Create dedicated styles for different drawing elements — for example, a larger bold style for titles and a smaller style for annotations.
- Text styles are stored in the DXF file, so drawings shared with other applications will retain their style definitions.
- Unused text styles can accumulate over time. Use the :doc:`/pages/commands/tools/purge` command (``P U``) to remove any styles that are no longer referenced by entities in the drawing.

----

See Also
--------

:doc:`/pages/layers` | :doc:`/pages/commands/entities/text` | :doc:`/pages/commands/tools/purge` | :doc:`/pages/dxf`
