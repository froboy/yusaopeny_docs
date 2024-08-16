---
title: Banner
description: A full-width, almost full-height display with a header, description, and call to action overlaid on an image. Also known as "Hero Banner".
---

{{< tabpane text=true >}}
  {{< tab header="Video" lang="vid" >}}
    {{< youtube kerfY3EBESA >}}
  {{< /tab >}}
  {{% tab header="Diagram" lang="pic" %}}
![Screenshot of the Banner component with block labels](lb--banner.png)
  {{% /tab %}}
{{< /tabpane >}}

-----

**Designs:**
- [Design System](../../../../../../assets/img/designs/lb-ui-kit/Banner.jpg)
- Pre-release: [Mobile](<../../../../../../assets/img/designs/lb/Hero Banner Mobile.png>) | [Desktop](<../../../../../../assets/img/designs/lb/Hero Banner Desktop.png>)

{{< readfile "../lb-add-block.partial" >}}

Fill in the content fields:

- **Title** (required): Never displayed, even if "Display Title" is checked. For administrative use only.
- **Banner Title** (required): A heading to display on the banner.
- **Description**: A full text editor to add banner content.
- **Media**: Chose from the library or add a new image or icon to be displayed behind the banner text.
- **CTA/Link**: A link at the bottom of the banner text.

{{< readfile "../lb-styles.partial" >}}

![Banner variants](../advanced-options/lb-advanced--banner-variants.png)

{{< readfile "../lb-save-block.partial" >}}
