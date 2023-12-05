---
title: Donate
description: A call to action with donation buttons linking to an embedded form.
---

> NOTE: This module requires per-provider configuration. Currently, support is provided for donation forms from:
> - **Blackbaud Online Express**, and
> - **Convio Luminate**.
>
> Please [submit a feature request](/roadmap) for additional provider support.

{{< tabpane text=true >}}
  {{< tab header="Video" lang="vid" >}}
    {{< youtube wPHimaZOprw >}}
  {{< /tab >}}
  {{% tab header="Diagram" lang="pic" %}}
![A screenshot of the Donate block.](lb-donate--block.png)
  {{% /tab %}}
{{< /tabpane >}}

**Designs:** [Mobile & Desktop](<../../../../../../assets/img/designs/lb-ui-kit/Donate.jpg>)

The **Y Layout Builder - Donate** (`lb_donate`) and **YMCA Website Services Donation Embed Form** (`y_donate`) modules work together allow content editors to add an embedded donation form to the site and create a separate call to action to direct users there.

## Embedded form

To get started:

1. Enable the **YMCA Website Services Donation Embed Form** (`y_donate`) module at **Administration** > **Extend**.
2. Select the **Layout** Tab of a Layout Builder-enabled page.
3. Select **Add block** on the page, then search or scroll to find **Donation Form Embed Block**.
4. Select the form type and enter the form ID from your donation provider.

### Troubleshooting

If your embedded form does not work in your non-production environment you may need to add a domain to the allow-list either on the provider-side or in your site's Content Security Policy.

If your provider is not listed you can add the form by selecting the **Code** Custom Block and then pasting in your code. Alternatively you can work with your development partner to [add a new donation provider](https://git.drupalcode.org/project/y_donate#information-for-developers).

## Donate Block

The Donate Block can be placed in an [edge-to-edge container](../advanced-options#layout-styles).

{{< readfile "../lb-add-block.partial" >}}

Fill in the content fields:

- **Title** (required): Never displayed, even if "Display Title" is checked. For administrative use only.
- **Section heading**: Displayed as a heading above the items.
- **Section subheading**: Displayed below the heading.
- **Giving amounts**: Any number of buttons with donation amounts. An "Other" button will always be displayed after all of these buttons.
  - **Amount label**: The amount to be displayed, with the currency sign, like "$50".
  - **Form Element ID**: Usually a 4-digit number found on the donation backend. You may need to find this on the donation platform side or in the browser inspector.
- **Donation page link**: A link to be displayed below the buttons.
  - **URL**: In order for the buttons to work properly, this must link to the page where the embedded donation form is embedded.
  - **Link text**: The text to be displayed.
- **Background image**: Chose from the library or add a new image to be displayed behind the text.

{{< readfile "../lb-save-block.partial" >}}
