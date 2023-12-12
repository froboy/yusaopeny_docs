---
title: Promotion
description:
---

Promotions are timed pieces of content that allow content editors the flexibility to create a single item that can be placed in multiple locations on the site, without having to duplicate or manage content in multiple locations.

## Fields

| Name                       | Machine name                 | Field type             | Required? |
|----------------------------|------------------------------|------------------------|-----------|
| Title                      | title                        |                        | yes       |
| Subtitle                   | field_subtitle               | Text (plain)           |           |
| CTA / link                 | field_link                   | Link                   | no        |
| Description                | field_promo_description      | Text (formatted, long) | no        |
| Image                      | field_promo_media            | Entity reference       | yes       |
| Pages                      | field_promo_visibility_pages | Text (plain, long)     |           |
| Promotion Category         | field_promo_category         | Entity reference       | no        |
| Promotion Priority         | field_promo_priority         | List (text)            | yes       |
| Promotion visibility state | field_promo_visibility_state | List (text)            | yes       |

## URL pattern

No URL pattern. This content should not be visible on its own.
