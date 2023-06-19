---
title: Table
description: Allows users to be able to view responsive tables within a page.
---

{{< tabpane text=true >}}
  {{< tab header="Video" lang="vid" >}}
    {{< youtube buxLFLUhiMo >}}
  {{< /tab >}}
  {{% tab header="Diagram" lang="pic" %}}
![Screenshot of the Table component with block labels](lb-table.png)
  {{% /tab %}}
{{< /tabpane >}}

-----

The Table block also allows users to add simple content to the Landing Page (Layout Builder) content type.

**Designs:**
- [Design System](../../../../../../assets/img/designs/lb-ui-kit/Table.jpg)
- Pre-release: [Mobile](<../../../../../../assets/img/designs/lb/Tables Mobile.png>) | [Desktop](<../../../../../../assets/img/designs/lb/Tables Desktop.png>)

{{< readfile "../lb-save-block.partial" >}}

Fill in the content fields:

- **Title** (required): Never displayed, even if _Display Title_ is checked. For administrative use only.
- **Section title**: Displayed as a heading above the item.
- **Section subtitle**: Displayed below the heading.
- **Body**: A full text editor to add tables or other content to the page. 
  - To add a table in the editor, click the **Table** icon, then configure the table options in the popup. ![A screenshot of the table icon and properties popup.](lb_table_icon.png)
  - To edit an existing table properties, right click in the table and then choose an option from the menu. ![A screenshot of the table operations menu.](lb_table_menu.png)

{{< readfile "../lb-save-block.partial" >}}