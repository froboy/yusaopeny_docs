---
title: 'Adding Links'
weight: 1
---

{{< youtube id=-AJLwiKC3oE >}}

-----

Links are simple in YMCA Website Services - just highlight your text and click the link icon (`🔗`) or type <kbd>Ctrl</kbd> / <kbd>Cmd</kbd> + <kbd>K</kbd>. Once the pop-up appears, type your URL into the field and click **Save**.

*[Read more and demo this on CKEditor Site.](https://ckeditor.com/docs/ckeditor5/latest/features/link.html)*

{{< tabpane text=true >}}
{{% tab header="CKEditor 5" lang="cke5" %}}
![The link button in the CKEditor 5 toolbar.](adding-links--cke5-toolbar.png "The link button in the CKEditor 5 toolbar.")
![The link popup in CKEditor 5.](adding-links--cke5-popup.png "The link popup in CKEditor 5.")
{{% /tab %}}
{{% tab header="CKEditor 4" lang="cke4" %}}
![The link button in the CKEditor 4 toolbar.](adding-links--cke4-toolbar.png "The link button in the CKEditor 4 toolbar.")
![The link popup in CKEditor 4.](adding-links--cke4-popup.png "The link popup in CKEditor 4.")
{{% /tab %}}
{{< /tabpane >}}

<hr />

## Advanced options

In the Advanced options of the link dialog, you can add attributes to links, including a label, HTML ID, and CSS classes. You can also opt to have your link open in a new window/tab.

{{< tabpane text=true >}}
{{% tab header="CKEditor 5" lang="cke5" %}}
![The advanced link options in CKEditor 5.](adding-links--cke5-advanced.png "The advanced link options in CKEditor 5.")
{{% /tab %}}
{{% tab header="CKEditor 4" lang="cke4" %}}
![The advanced link options in CKEditor 4.](adding-links--cke4-advanced.png "The advanced link options in CKEditor 4.")
{{% /tab %}}
{{< /tabpane >}}

## Linking tips

* For links on your website, don’t use the full URL. Delete everything beginning with the `/` after your `.com`, `.org`, etc.
  * For example, for ymca.org/about, you would choose /about. This is called the relative path, and it will help your analytics tracking.
* For links on other websites, grab the full URL, including the `https://`.
  * For example, for example.org/about, you would choose https://example.org/about.
* For email links, add `"mailto:example@example.org."`

To update/change a link, click on the link text then click the link icon or use the popup options (in CKEditor 5).

To remove a link, highlight the link text and click the unlink icon.

## Improving internal linking with Linkit

A community-contributed module, [Linkit](https://www.drupal.org/project/linkit)

> provides an autocomplete interface for internal and external linking in rich-text editors. Linkit supports nodes, users, taxonomy terms, files, comments and basic support for all types of entities that define a canonical link template.

Drupal core will [soon provide link autocomplete suggestions](https://www.drupal.org/project/drupal/issues/3317769) in CKEditor similar to what this module does. Until that issue is complete, developers may want to [install and configure Linkit](https://www.drupal.org/project/linkit) to improve the linking experience in the WYSIWYG editor.