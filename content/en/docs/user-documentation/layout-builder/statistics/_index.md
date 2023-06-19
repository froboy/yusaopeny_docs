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
- **Section title**: Displayed as a heading above the item.
- **Section subtitle**: Displayed below the heading.
- **Media**: Chose from the library or add a new image to be displayed to the left of the statistics.
- **Section CTA/Link**: Add a link below the statistics items.
- **Statistics Items**: Add as many items as you like using the **Add Statistics Item** button. Each item contains:
  - **Number value**: The number value for the statistic. Can include a prefix ("$100") and/or suffix ("$100M").
  - **Description**: A description of the statistic.

{{< readfile "../lb-save-block.partial" >}}