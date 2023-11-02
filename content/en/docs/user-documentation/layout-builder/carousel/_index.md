---
title: Carousel
description: A full-width gallery with multiple sets of a header, description, and call to action overlaid on top of an image.
---

{{< tabpane text=true >}}
  {{< tab header="Video" lang="vid" >}}
    {{< youtube zVT1St0UXsk >}}
  {{< /tab >}}
  {{% tab header="Diagram" lang="pic" %}}
![Screenshot of the Carousel component with block labels](lb-carousel.png)
  {{% /tab %}}
{{< /tabpane >}}

-----

**Designs:**
- [Design System](../../../../../../assets/img/designs/lb-ui-kit/Carousel.jpg)
- Pre-release: [Mobile](<../../../../../../assets/img/designs/lb/Carousels Mobile.png>) | [Desktop](<../../../../../../assets/img/designs/lb/Carousels Desktop.png>)

{{< readfile "../lb-add-block.partial" >}}

Fill in the content fields:

- **Title** (required): Never displayed, even if "Display Title" is checked. For administrative use only.
- **Carousel heading**: Displayed as a heading above the carousel.
- **Carousel subheading**: Displayed below the heading.
- **Carousel Item**: Add as many items as you like using the **Add Carousel Item** or **Add new custom block** button. When you are finished adding or editing each item, be sure to click **Create/Update tab** or **Create/Update custom block** to finalize the item. Each item contains:
  - **Heading**
  - **Image**: Chose from the library or add a new image.
  - **Description**
  - **Link**: A link at the bottom of the carousel item.

{{< readfile "../lb-save-block.partial" >}}
