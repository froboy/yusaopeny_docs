---
title: Landing Page (Layout Builder)
---

Landing Page content type is used to add Landing Pages to your website using Layout Builder widgets.

This page is managed with Layout Builder. You may want to uncheck "Publish Content" before creating a page, use the "Layout" tab to build the content, then Publish when the page is complete. See our [User Guide](../../user-documentation/layout-builder) for help.

## Fields

| Label            | Machine Name           | Required | Description                                         | Field Settings                 | Notes |
|------------------|------------------------|----------|-----------------------------------------------------|--------------------------------|-------|
| Title            | title                  | yes      | Title of Landing Page                               |                                |       | |
| **Metadata**     | Field group            |
| Meta description | field_meta_description | no       | Short text used for metatags and cards              | Text (plain, long)             |       |
| Meta image       | field_meta_image       | no       | Media image reference for use in metatags and cards | Entity reference (Media image) |       |
| Meta tags        | field_meta_tags        | no       | Provided by Metatag module                          |                                |       |

## URL pattern

Content type is using following pattern: `[node:title]`
