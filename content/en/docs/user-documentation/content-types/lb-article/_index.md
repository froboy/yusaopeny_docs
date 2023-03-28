---
title: Article (Layout Builder)
description: The Article content type combines all news-related content into a single content type.
weight: -1
---

This gives content editors the ability to vary the layout and views display depending on the type of article created (news item, blog post, or press release). This way, if an association wants to display news items on a news page, and blog posts on a blog page, they can differentiate based on where they would like the article to display on the site.

Article also allows content editors to include Layout Builder components within the page.

**Designs:** [Mobile](<../../../../../../assets/img/designs/lb/Article Mobile.png>) | [Desktop](<../../../../../../assets/img/designs/lb/Article Desktop.png>)

{{% youtube FBtQmfy9C7Q %}}

## Creating an Article

Go to **Admin** > **Content** > **Add Content** > **Article (Layout Builder)**

Fill in the content fields:

- **Title** (required)
- **Subtitle**
- **Type**: Select "Blog", "News", or "Press Release". Each type has the same fields, but allows admins to group articles for display on different pages (i.e. Blog types will display on a Blog page, Press Releases on a Press Release page, etc.)
- **Header image**: This image is displayed on the Article page and in listing views.
- **Tags**: References terms in the Tags vocabulary. See [Taxonomy](../../taxonomy) for more information on tags.
- **Body** (required): Add text with the [WYSIWYG editor](../../text-editor)
- **Locations**: If the Article relates to a [Branch](../branch) then select it here so that the Article shows in listings on the Branch page.
- **Published Date** (required): Defaults to today. This is the date that will be displayed on the Article page, used for sorting, and in listings.

## Customizing Articles

Once you create an Article you can customize the layout with [Layout Builder](../../layout-builder). These components are built specifically to work with the Article content type:

- [Related Articles](../../layout-builder/related-articles)
