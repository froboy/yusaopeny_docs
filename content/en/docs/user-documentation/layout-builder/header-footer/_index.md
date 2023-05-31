---
title: Header/Footer
description: Many blocks come together to create a configurable header and footer for Layout Builder pages.
---

{{< tabpane text=true >}}
  {{< tab header="Video" lang="vid" >}}
    {{< youtube  >}}
  {{< /tab >}}
  {{% tab header="Diagram" lang="pic" %}}
![Screenshot of the Header Section with block labels](lb-header-footer--header.png)
![Screenshot of the Footer Section with block labels](lb-header-footer--footer.png)
  {{% /tab %}}
{{< /tabpane >}}

**Designs:** 

- [Utility Menu Mobile & Desktop](<../../../../../../assets/img/designs/lb-ui-kit/Utility Menu.jpg>)
- [Menu & Search Mobile & Desktop](<../../../../../../assets/img/designs/lb-ui-kit/Menu and Search.jpg>)
- [Header Mobile & Desktop](<../../../../../../assets/img/designs/lb-ui-kit/Global Header.jpg>)
- [Footer Mobile & Desktop](<../../../../../../assets/img/designs/lb-ui-kit/Global Footer.jpg>)

The header and footer on Layout Builder pages is composed of many complimentary blocks. The Header and Footer are special Sections that are pre-populated on each Layout Builder-enabled content type. If the Header or Footer do not already exist in your content, you can add them on your own.

## Header Section
![Screenshot of the Header Section with block labels](lb-header-footer--header.png)

If a Header section does not already exist, add a new Section and choose the **WS Header** Layout. Then, add the following blocks by selecting **Add block** and then using the search box under **All system blocks**:

- Utility Menu area
  - Left
    - **Website Name Block**
  - Right
    - **Open Y Google Translate Block**
- Main Menu area
  - Left
    - **Site Logo Block**
  - Center
    - **Main navigation**
    - **Search Bar Block**
  - Right
    - **User account menu**

Each block has some specific configuration recommendations:

### Website Name Block

**Configuration**

- Uncheck **Display title**.

**Content**

- The **Site Name** is found under **Configuration** > **System** > **Basic site settings**.

### Open Y Google Translate Block

**Configuration**

- Uncheck **Display title**.

**Content**

- The contents of this block are not configurable, but it may be omitted or removed if your site does not provide translation uses another translation method.

### Site Logo Block

**Configuration**

- **Title (required):** Never displayed, even if “Display Title” is checked. For administrative use only.
- **WS Site Logo:** Choose which logo is displayed in the block.
  - **Theme logo** uses the logo defined by the active theme, in the **Appearance** > **Settings** > **(The active theme)**.
  - **Colorway logo** uses a dynamic SVG that responds to the configured YMCA colorway. This option is recommended for the Header.
  - **White logo** uses a flat white logo. This option is recommended for the Footer.

### Main navigation

**Configuration**

- Uncheck **Display title**.
- **Menu levels** controls which and how many levels of menu are displayed. We recommend using the default configuration.

**Content**

- Menu items can be managed under **Structure** > **Menus** > **Main navigation**.

{{< alert color="warning" title="Tip" >}}
Refer to the Drupal User Guide for more information about [managing menus](https://www.drupal.org/docs/user_guide/en/menu-concept.html).
{{< /alert >}}

### Search Bar Block

**Configuration**

- Uncheck **Display title**.

**Content**

- The contents of this block are not configurable.

### User account menu

**Configuration**

- Uncheck **Display title**.
- **Menu levels** controls which and how many levels of menu are displayed. We recommend using the default configuration.

**Content**

- Menu items can be managed under **Structure** > **Menus** > **User account**.

## Footer Section

![Screenshot of the Footer Section with block labels](lb-header-footer--footer.png)

If a Footer section does not already exist, add a new Section and choose the **WS Footer** Layout. Then, add the following blocks by selecting **Add block** and then using the search box under **All system blocks**:

- Primary Footer
  - Site Logo
  - Footer Menu Left
  - Footer Menu Center
  - Footer Menu Right
  - Footer Social
- Sub-footer
  - Copyright
  - Footer Menu

### Site Logo

[See above](#site-logo-block). The "white logo" is recommended for the footer.

### Footer Menu Left, Center, Right

Each of these three blocks references a menu. The three menus can be used to split footer links across multiple columns.

**Configuration**

- **Display title:** Uncheck to hide the title, or turn the menu title on to give each column a title.
- **Menu levels** controls which and how many levels of menu are displayed. We recommend using the default configuration.

**Content**

- Menu items can be managed under **Structure** > **Menus** > **Footer Menu Left**, **Footer Menu Center**, or **Footer Menu Right**.

### Footer Social

**Configuration**

- **Display title:** It's up to you.

**Content**

- [Edit the Footer Social Block](/docs/user-documentation/virtual-ymca/managing-footer-links/) to modify this block.

### Copyright

**Configuration**

- Uncheck **Display title**.

**Content**

- Go to **Structure** > **Block layout** > **Custom block library**
- Find the **Footer Copyright Block**
- **Edit** the block, then **Save** when finished.

### Footer Menu

This menu is typically for a limited number of links such as "Privacy Policy" or "Terms of Use".

**Configuration**

- Uncheck **Display title**.
- **Menu levels** controls which and how many levels of menu are displayed. We recommend using the default configuration.

**Content**

- Menu items can be managed under **Structure** > **Menus** > **Footer**.
