---
title: Event
---

Event content type is used for adding events on the site.


### Fields
| Label            | Machine Name           | Required               | Description | Field Settings | Notes |
|------------------|------------------------|--------------------|----------|----------------|-------|
| Title  | drupal's default  | Yes | Title of the event item. |
| Sub-title | default?? | No | Sub-title of the event item. | plain text |
| Locations | field\_event_location | Yes | Reference field to `branch` and `camp` nodes. Multiple Values. | | Address for event; can be either a branch or non-branch location.
| Category | field\_event_category | No | Reference field for choosing the term from "Event Category" vocabulary. Multiple Values. |
| Meta Tags  | field\_meta_tags  | No | A meta tags field allows us to provide structured metadata and Graph meta tags for Facebook, Pinterest, LinkedIn and other social networking sites. |
| Image | field\_event_image | No | Image field for the Event item. Entity reference to Media bundle. | media | 
| Date | field\_event_date | Yes | This will use Drupal date/time fields. |
| Add to Calendar | field\_add_to_calendar_link | No | | link |
| Body | body | No | Textarea for the description/body with WYSIWYG, without summary. |
| Content | field\_content | No | Filter list of available layout builder components |
| Related Content | field\_event_related | No | Reference field for choosing related Event nodes. Multiple Values. |

### URL pattern
Content type is using following pattern:
`/event/[node:title]`
