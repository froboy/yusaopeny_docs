---
title: Partners
description: Component for displaying logos / info of partners or sponsors within a page using Layout Builder.
---

{{< tabpane text=true >}}
    {{< tab header="Video" lang="vid" >}}
        {{< youtube nHxIX6fuTAM >}}
    {{< /tab >}}
    {{% tab header="Diagram" lang="pic" %}}
![Screenshot showing the field titles overlaid on the design](lb-partners-fields.png)
    {{% /tab %}}
{{< /tabpane >}}

-----

**Designs:**
- [Design System](../../../../../../assets/img/designs/lb-ui-kit/Sponsors.jpg)
- Pre-release: [Mobile](<../../../../../../assets/img/designs/lb/Sponsors Mobile.png>) | [Desktop](<../../../../../../assets/img/designs/lb/Sponsors Desktop.png>)

{{< readfile "../lb-add-block.partial" >}}

Fill in the content fields:

- **Title** (required): Never displayed, even if "Display Title" is checked. For administrative use only.
- **Section heading**: Displayed as a heading above the items.
- **Section subheading**: Displayed below the heading.
- **Partner items**: Click **Add new custom block** to add a new Partner item, or **Add existing custom block** to reuse an existing item. Items can be reused across pages. Add unlimited items. Each item has:
  - **Heading**: The name of the partner.
  - **Image**: The logo or image.
  - After filling in the fields for an item, click **Create custom block** to save the item.

{{< readfile "../lb-save-block.partial" >}}
