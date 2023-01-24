---
title: Article
---

Article content type is used for adding blog posts, news items, and press releases on the site.

### Fields
| Name | Machine name | Required | Description |
| ------------- | ------------- | ------------- | ------------- | 
| Title  | drupal's default  | Yes | Title of the article item. |
| Sub-title | default?? | No | Sub-title of the article item
| Locations | field\_article_location | Yes | Reference field to `branch` and `camp` nodes. Multiple Values. |
| Category | field\_article_category | No | Reference field for choosing the term from "Blog Category" vocabulary. Multiple Values. |
| Meta Tags  | field\_meta_tags  | No | A meta tags field allows us to provide structured metadata and Graph meta tags for Facebook, Pinterest, LinkedIn and other social networking sites. |
| Type | field\_article_type  | Yes | Select list field with multiple options for choosing article type: <ul><li>News Item (default)</li><li>Blog Post</li><li>Press Release</li></ul> |
| Image | field\_article_image | No | Image field for the Blog item. Entity reference to Media bundle. | 
| Body | body | No | Textarea for the description/body with WYSIWYG, without summary. |
| Content | field\_content | No | Filter list of available layout builder components |
| Related Content | field\_article_related | No |Reference field for choosing related Article nodes. Multiple Values. |

### URL pattern
Content type is using following pattern:
`/blog/[node:title]`
`/news/[node:title]`
`/press-release/[node:title]`
