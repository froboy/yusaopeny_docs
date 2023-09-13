---
title: How to integrate with social media
linkTitle: "... integrate social media"
description: Embedded social feeds or posts can help share your message with users. 
aliases:
  - /docs/development/addthis/
  - /docs/development/configuration-for-social-posts-import/
---

Social media is a great platform for communicating with your Y community, and it's often helpful to embed feeds or posts in a page to share topical content with users. 

The distribution has used a number of methods over the years to add social content to sites, but all of them are dependent on the specific platforms maintaining open APIs. Unfortunately many social networks are now locking down and restricting their APIs.

## How to embed social content in your YMCA website (in 2023)

Currently, we recommend using embed codes from the specific platform in order to embed social posts or feeds on your YMCA Website Services website.

### Find the embed code

Each platform has its own way of doing embeds. For posts, you can often find an "Embed" button in the options or share menu. For feeds, you often need to use a separate builder. Here are some options we've found:

- [Twitter / 𝕏 Publish](https://publish.twitter.com/)
- [Meta (Facebook/Instagram) Social Plugins](https://developers.facebook.com/docs/plugins)

> **Note:** Social platforms may break these embeds at their whim. Use at your own risk.

### Embeds using Paragraphs

- Navigate to a content page on your site, then click **Edit**.
- Add a [Code Paragraph](../../user-documentation/paragraphs/code) to the section where you'd like to do the embed.
- Paste in the embed code generated above.
- **Save** the page.

### Embeds using Layout Builder

- Navigate to a content page on your site, then click **Layout**.
- Add a [Code Block](../../user-documentation/layout-builder/code)to the section where you'd like to do the embed.
- Paste in the embed code generated above.
- **Save** the block, then **Save layout** on the page.

### Alternatively, try Social Feeds Fetcher

The [Social Feeds Fetcher module](https://www.drupal.org/project/social_feed_fetcher) that comes with the distribution allows your site to import social media content for syndication.

To configure fetching:

- Open the configuration page at `/admin/config/social_feed_fetcher_settings` or **Configuration** > **Web Services** > **Social Feed Fetcher Settings**
- Select the checkbox for your chosen social networks and add additional settings. Every social network has their own API and requires different configuration.
- When all settings are completed, click **Run Cron**. The import is started and if the configuration is correct, items will appear in the content list.

## How to share content from your site to social media

> All mobile browsers — Firefox, Edge, Safari, Chrome, Opera Mini, UC Browser, Samsung Internet — make it easy to share content directly from their native platforms.
> 
> -- [UX Considerations for Web Sharing](https://css-tricks.com/ux-considerations-for-web-sharing/)

### Using AddThis

This [Social Share Icons](../../user-documentation/paragraphs/social-share-icons) paragraph and the [AddThis module](https://www.drupal.org/project/openy_addthis) ceased functioning on May 31, 2023, with the discontinuation of [AddThis](https://www.addthis.com/) services.