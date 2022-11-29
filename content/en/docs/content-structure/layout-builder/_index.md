---
title: Layout Builder
---

These custom block types exist to support page building with Layout Builder.

### Global Fields

These fields are reused across many of the below components.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section title | field_section_title | Text (plain) | no | 1 |
| Section subtitle | field_section_subtitle | Text (plain, long) | no | 1 |

## Accordion

**Machine name:** `lb_accordion`

Expandable pairs of question/answer or header/section fields.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Accordion Item | field_entity_reference_paragraph | Entity reference revisions | no | unlimited | | Bundle: accordion_item |

### Accordion Item

**Machine name:** `lb_accordion_item`

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Title | field_title | Text (plain) |
| Body | field_body | Text (formatted, long, with summary) |

## Cards

**Machine name:** `lb_cards`

Flexible card-style components that allow up to 4 cards to display across the page depending on the chosen layout.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section title | (inherit) | 
| Section subtitle | (inherit) | 
| Section CTA/Link | field_cta | Link | no | 1 |
| # of columns | field_columns | List (text) | no | 1 | Choose "none" for one-column. | 
| Cards | field_cards | Entity reference revisions | no | 4 | | Bundle: Card

### Card

**Machine name:** `lb_card`

The Card paragraph is referenced by the Cards block.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Title | field_card_title | Text (plain) | yes | 1 |
| Image | field_card_image | Entity reference |  no | 1 |
| Topic Tag | field_card_topic_tag | Text (plain) | no | 1 | | | May be changed to term. |
| Description | field_card_description | Text (plain, long) | no | 1 |
| CTA/Link | field_card_cta | Link | no | 1 |

## Grid CTA

**Machine name:** `lb_grid_cta`

Sets of content with a headline, description, and link displayed in 2 to 4-item wide rows, with the option to include icons or images.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section title | (inherit) |
| Section subtitle | (inherit) |
| Grid section CTA/link | field_grid_section_cta_link | Link | no | 1 | A link button to be displayed below the grid content |
| # of columns | field_columns | List (text) | yes | 1 | | | Allows 2-4 columns, defaults to 4. |
| Grid Items | field_grid_items | Entity Reference | yes | unlimited | | Bundle: Grid Item

### Grid Item

**Machine name:** `lb_cta_item`

The Grid Item paragraph is referenced by the Grid CTA component.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Grid item title | field_grid_item_title | Text (plain) | no | 1 |
| Grid item description | field_grid_item_description | Text (formatted, long) | no | 1 |
| Grid item media | field_grid_item_icon | Entity reference | no | 1 |
| Grid item CTA/link | field_grid_item_cta_link | Link | no | 1 |

## Hero Banner

**Machine name:** `lb_hero`

A full-width, almost full-height display with a header, description, and call to action overlaid on an image.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Title | field_title | Text (plain) | yes | 1 |
| Description | field_description | Text (formatted, long) | no | 1 | 
| Media | field_media | Entity reference | no | 1 | | Bundle: Image, Local Video, Video |
| CTA\Link | field_hero_cta | Link | no | 1 |

## Ping-pong

**Machine name:** `lb_ping_pong`

Usually paired sets of full-width page components that include media, header, description, and call to action arranged horizontally.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section subtitle | field_subtitle | (inherit) |
| Section Title | field_title | (inherit) |
| Item title | field_item_title | Text (plain) | no | 1 |
| Item Description | field_item_description | Text (formatted, long) | no | 1 |
| Item CTA\Link | field_item_cta | Link | no | 2 | The first will use the primary style and the second, secondary. |
| Item Image | field_item_image | Entity reference | no | 1 |
| Item Image Position | field_item_image_position | List (text) | yes | 1 | Places the image on this side of the page in the full-width display. Image will always be above Description on at narrow widths. 

## Promo Card

**Machine name:** `lb_promo`

A title, headline, description, and link that usually display in the right or left sidebar.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Title | field_title | Text (plain) | yes | 1 |
| Body | body | Text (formatted, long, with summary) | no | 1 | 
| Icon / Image | field_image | Entity reference | no | 1 | | Bundle: Image |
| CTA / Link | field_cta | Link | no | 1 |

## Simple Menu

**Machine name:** `lb_simple_menu`

A simple 1-level sidebar menu that can display in either the right or left sidebar area.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Icon | field_icon | Entity reference | no | 1 | | Bundle: Image |
| Links | field_lb_simple_menu_links | Link | yes | unlimited |

## Tabs

**Machine name:** `lb_tabs`

Gives users the ability to switch page views by selecting tabs across the top of the page instead of having to navigate to a new page.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Section title | (inherit) | 
| Section subtitle | (inherit) | 
| Tabs | field_tabs | Entity reference revisions | no | unlimited | | Bundle: Tab |

### Tab

**Machine name:** `tab`

The Tab paragraph is referenced by the Tabs block.

| Label | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
| ----- | ------------ | ---- | -------- | ----------- | --------- | -------------- | ----- |
| Title | field_title | Text (plain) | yes | 1 |
| Body | field_body | Text (formatted, long, with summary) | no | 1 |
