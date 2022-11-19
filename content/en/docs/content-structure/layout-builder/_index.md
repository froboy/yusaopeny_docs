---
title: Layout Builder Blocks
---

These custom block types exist to support page building with Layout Builder.

## Global Fields

These fields are reused across many of the below components.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section title | field_section_title | Text (plain) | no | 1 |
| Section subtitle | field_section_subtitle | Text (plain, long) | no | 1 |

## Custom Blocks

### Accordion

Machine name: `lb_accordion`

A component for adding custom Accordions.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Accordion Item | field_entity_reference_paragraph | Entity reference revisions | no | unlimited | | Bundle: accordion_item |

#### Accordion Item

Machine name: `lb_accordion_item`

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Title | field_title | Text (plain) |
| Body | field_body | Text (formatted, long, with summary) |

### Grid CTA

Machine name: `lb_grid_cta`

Grid CTA Layout Builder component.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section title | (inherit) |
| Section subtitle | (inherit) |
| Grid section CTA/link | field_grid_section_cta_link | Link | no | 1 | A link button to be displayed below the grid content |
| # of columns | field_columns | List (text) | yes | 1 | | | Allows 2-4 columns, defaults to 4. |
| Grid Items | field_grid_items | Entity Reference | yes | unlimited | | Bundle: Grid Item

#### Grid Item

Machine name: `lb_cta_item`

The Grid Item paragraph is referenced by the Grid CTA.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Grid item title | field_grid_item_title | Text (plain) | no | 1 |
| Grid item description | field_grid_item_description | Text (formatted, long) | no | 1 |
| Grid item media | field_grid_item_icon | Entity reference | no | 1 |
| Grid item CTA/link | field_grid_item_cta_link | Link | no | 1 |

### Ping-pong

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section subtitle | field_subtitle | (inherit) |
| Section Title | field_title | (inherit) |
| Item title | field_item_title | Text (plain) | no | 1 |
| Item Description | field_item_description | Text (formatted, long) | no | 1 |
| Item CTA\Link | field_item_cta | Link | no | 2 | The first will use the primary style and the second, secondary. |
| Item Image | field_item_image | Entity reference | no | 1 |
| Item Image Position | field_item_image_position | List (text) | yes | 1 | Places the image on this side of the page in the full-width display. Image will always be above Description on at narrow widths. 
