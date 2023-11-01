---
title: Statistics
description: Infographic-like display that highlights relevant statistics to users.
---

{{< tabpane text=true >}}
  {{< tab header="Video" lang="vid" >}}
    {{< youtube _RQcnMw4X5U >}}
  {{< /tab >}}
  {{% tab header="Diagram" lang="pic" %}}
![Screenshot of the Statistics component with block labels](lb-statistics.png)
  {{% /tab %}}
{{< /tabpane >}}

-----

**Designs:**
- [Design System](../../../../../../assets/img/designs/lb-ui-kit/Statistics.jpg)
- Pre-release: [Mobile](<../../../../../../assets/img/designs/lb/Statistics Mobile.png>) | [Desktop](<../../../../../../assets/img/designs/lb/Statistics Desktop.png>)

{{< readfile "../lb-add-block.partial" >}}

Fill in the content fields:

- **Title** (required): Never displayed, even if "Display Title" is checked. For administrative use only.
- **Section heading**: Displayed as a heading above the item.
- **Section subheading**: Displayed below the heading.
- **Media**: Chose from the library or add a new image to be displayed to the left of the statistics.
- **Section link**: Add a link below the statistics items.
- **Statistics items**: Add as many items as you like using the **Add Statistics Item** or **Add new custom block** button. When you are finished adding or editing each item, be sure to click **Create/Update tab** or **Create/Update custom block** to finalize the item. Each item contains:
  - **Number value**: The number value for the statistic. Can include a prefix ("$100") and/or suffix ("$100M").
  - **Description**: A description of the statistic.

{{< readfile "../lb-save-block.partial" >}}
