---
title: Icon Grid
description: A simpler version of the Grid CTA component. Sets of content with a headline and description displayed in 2 to 4-item wide rows, with the option to include icons or images.
---

{{< tabpane text=true >}}
  {{< tab header="Video" lang="vid" >}}
    {{< youtube cYbSqcoOMWg >}}
  {{< /tab >}}
  {{% tab header="Diagram" lang="pic" %}}
![Screenshot of the Icon Grid component with block labels](lb-icon-grid.png)
  {{% /tab %}}
{{< /tabpane >}}

-----

The Icon Grid block is similar to the [Cards](../cards) and [Grid CTA](../grid-cta) blocks, but allows for more simpler items with a slightly more restricted design.

**Designs:**
- [Design System](<../../../../../../assets/img/designs/lb-ui-kit/Icon Grid.png>)

{{< readfile "../lb-add-block.partial" >}}

Fill in the content fields:

- **Title** (required): Never displayed, even if "Display Title" is checked. For administrative use only.
- **Section heading**: Displayed as a heading above the cards.
- **Section subheading**: Displayed below the heading.
- **Icon Grid section link**: A link button displayed below the list of items.
- **# of columns**: Allows 2- to 4-columns of items.
- **Grid Icon Items**: Add up to 4. Each item has:
  - **Title** (required)
  - **Description**: A full text editor to add item content.
  - **Icon**: Chose from the library or add a new image or icon to be displayed above the item text. Circular icons are recommended. All icon/images will be displayed with a circular crop.

{{< readfile "../lb-save-block.partial" >}}
