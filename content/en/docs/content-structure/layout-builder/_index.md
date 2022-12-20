---
title: Layout Builder
---

These custom block types exist to support page building with Layout Builder.

### Global Fields

These fields are reused across many of the below components.

| Label            | Machine Name           | Type               | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|------------------------|--------------------|----------|-------------|-----------|----------------|-------|
| Section title    | field_section_title    | Text (plain)       | no       | 1           |
| Section subtitle | field_section_subtitle | Text (plain, long) | no       | 1           | 

## Accordion

- **Machine name:** `lb_accordion`
- **Project:** [lb_accordion](https://www.drupal.org/project/lb_accordion)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Accordion Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Accordion Desktop.png>)

Expandable pairs of question/answer or header/section fields.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Accordion Item | field_entity_reference_paragraph | Entity reference revisions | no       | unlimited   |           | Bundle: accordion_item |

### Accordion Item

- **Machine name:** `lb_accordion_item`

| Label | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|-------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Title | field_title  | Text (plain)                         | yes      | 1           |
| Body  | field_body   | Text (formatted, long, with summary) | no       | 1           |

## Cards

- **Machine name:** `lb_cards`
- **Project:** [lb_cards](https://www.drupal.org/project/lb_cards)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Cards Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Cards Mobile.png>)

Flexible card-style components that allow up to 4 cards to display across the page depending on the chosen layout.

| Label            | Machine Name  | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|---------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Section title    | (inherit)     | 
| Section subtitle | (inherit)     | 
| Section CTA/Link | field_cta     | Link                       | no       | 1           |
| # of columns     | field_columns | List (text)                | yes      | 1           |           | 
| Cards            | field_cards   | Entity reference revisions | no       | 4           |           | Bundle: Card   |

### Card

**Machine name:** `lb_card`

The Card paragraph is referenced by the Cards block.

| Label       | Machine Name           | Type               | Required | Cardinality | Help text | Field Settings | Notes                   |
|-------------|------------------------|--------------------|----------|-------------|-----------|----------------|-------------------------|
| Title       | field_card_title       | Text (plain)       | yes      | 1           |
| Image       | field_card_image       | Entity reference   | no       | 1           |
| Topic Tag   | field_card_topic_tag   | Text (plain)       | no       | 1           |           |                | May be changed to term. |
| Description | field_card_description | Text (plain, long) | no       | 1           |
| CTA/Link    | field_card_cta         | Link               | no       | 1           |

## Carousel

- **Machine name:** `lb_carousel`
- **Project:** [lb_carousel](https://www.drupal.org/project/lb_carousel)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Carousels Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Carousels Desktop.png>)

A full-width display with multiple sets of a header, description, and call to action overlaid on top of an image.

| Label             | Machine Name         | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|-------------------|----------------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Carousel title    | field_section_title  | Text (plain)               | no       | 1           |
| Carousel subtitle | field_subtitle       | Text (plain)               | no       | 1           |
| Carousel Items    | field_carousel_items | Entity reference revisions | no       | unlimited   |

### Carousel Item

**Machine name:** `lb_carousel_item`

| Label       | Machine Name               | Type                   | Required | Cardinality | Help text | Field Settings | Notes |
|-------------|----------------------------|------------------------|----------|-------------|-----------|----------------|-------|
| Title       | field_title                | Text (plain)           | no       | 1           |
| Image       | field_carousel_image       | Entity reference       | no       | 1           |
| Description | field_carousel_description | Text (formatted, long) | no       | 1           |
| CTA \ Link  | field_carousel_cta         | Link                   | no       | 1           |

## Grid CTA

- **Machine name:** `lb_grid_cta`
- **Project:** [lb_grid_cta](https://www.drupal.org/project/lb_grid_cta)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Grid Content Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Grid Content Desktop.png>)

Sets of content with a headline, description, and link displayed in 2 to 4-item wide rows, with the option to include icons or images.

| Label                 | Machine Name                | Type             | Required | Cardinality | Help text                                            | Field Settings    | Notes                              |
|-----------------------|-----------------------------|------------------|----------|-------------|------------------------------------------------------|-------------------|------------------------------------|
| Section title         | (inherit)                   |
| Section subtitle      | (inherit)                   |
| Grid section CTA/link | field_grid_section_cta_link | Link             | no       | 1           | A link button to be displayed below the grid content |
| # of columns          | field_columns               | List (text)      | yes      | 1           |                                                      |                   | Allows 2-4 columns, defaults to 4. |
| Grid Items            | field_grid_items            | Entity Reference | yes      | unlimited   |                                                      | Bundle: Grid Item |

### Grid Item

**Machine name:** `lb_cta_item`

The Grid Item paragraph is referenced by the Grid CTA component.

| Label                 | Machine Name                | Type                   | Required | Cardinality | Help text | Field Settings | Notes |
|-----------------------|-----------------------------|------------------------|----------|-------------|-----------|----------------|-------|
| Grid item title       | field_grid_item_title       | Text (plain)           | no       | 1           |
| Grid item description | field_grid_item_description | Text (formatted, long) | no       | 1           |
| Grid item media       | field_grid_item_icon        | Entity reference       | no       | 1           |
| Grid item CTA/link    | field_grid_item_cta_link    | Link                   | no       | 1           |

## Hero Banner

- **Machine name:** `lb_hero`
- **Project:** [lb_hero](https://www.drupal.org/project/lb_hero)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Hero Banner Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Hero Banner Desktop.png>)

A full-width, almost full-height display with a header, description, and call to action overlaid on an image.

| Label       | Machine Name      | Type                   | Required | Cardinality | Help text | Field Settings                    | Notes |
|-------------|-------------------|------------------------|----------|-------------|-----------|-----------------------------------|-------|
| Title       | field_title       | Text (plain)           | yes      | 1           |
| Description | field_description | Text (formatted, long) | no       | 1           | 
| Media       | field_media       | Entity reference       | no       | 1           |           | Bundle: Image, Local Video, Video |
| CTA\Link    | field_hero_cta    | Link                   | no       | 1           |

## Ping-pong

- **Machine name:** `lb_ping_pong`
- **Project:** [lb_ping_pong](https://www.drupal.org/project/lb_ping_pong)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Ping Pong Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Ping Pong Desktop.png>)

Usually paired sets of full-width page components that include media, header, description, and call to action arranged horizontally.

| Label               | Machine Name              | Type                   | Required | Cardinality | Help text                                                                                                          | Field Settings | Notes |
|---------------------|---------------------------|------------------------|----------|-------------|--------------------------------------------------------------------------------------------------------------------|----------------|-------|
| Section subtitle    | field_subtitle            | (inherit)              |
| Section Title       | field_title               | (inherit)              |
| Item title          | field_item_title          | Text (plain)           | no       | 1           |
| Item Description    | field_item_description    | Text (formatted, long) | no       | 1           |
| Item CTA\Link       | field_item_cta            | Link                   | no       | 2           | The first will use the primary style and the second, secondary.                                                    |
| Item Image          | field_item_image          | Entity reference       | no       | 1           |
| Item Image Position | field_item_image_position | List (text)            | yes      | 1           | Places the image on this side of the page in the full-width display. Image will stack above text at narrow widths. |

## Partners

- **Machine name:** `lb_partners`
- **Project:** [lb_]
- **Designs:** [Mobile](<>) | [Desktop](<>)

List of multiple partner / sponsor logos.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|


## Promo Card

- **Machine name:** `lb_promo`
- **Project:** [lb_promo](https://www.drupal.org/project/lb_promo)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Promo Cards Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Promo Cards Desktop.png>)

A title, headline, description, and link that usually display in the right or left sidebar.

| Label        | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|--------------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Title        | field_title  | Text (plain)                         | yes      | 1           |
| Body         | body         | Text (formatted, long, with summary) | no       | 1           | 
| Icon / Image | field_image  | Entity reference                     | no       | 1           |           | Bundle: Image  |
| CTA / Link   | field_cta    | Link                                 | no       | 1           |

## Simple Menu

- **Machine name:** `lb_simple_menu`
- **Project:** [lb_simple_menu](https://www.drupal.org/project/lb_simple_menu)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Simple Menu Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Simple Menu Desktop.png>)

A simple 1-level sidebar menu that can display in either the right or left sidebar area.

| Label | Machine Name               | Type             | Required | Cardinality | Help text | Field Settings | Notes |
|-------|----------------------------|------------------|----------|-------------|-----------|----------------|-------|
| Icon  | field_icon                 | Entity reference | no       | 1           |           | Bundle: Image  |
| Links | field_lb_simple_menu_links | Link             | yes      | unlimited   |

## Statistics

- **Machine name:** `lb_statistics`
- **Project:** [lb_statistics](https://www.drupal.org/project/lb_statistics)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Statistics Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Statistics Desktop.png>)

Infographic-like display that highlights relevant statistics to users.

| Label              | Machine Name  | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|--------------------|---------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Section title      | (inherit)     |
| Section subtitle   | (inherit)     |
| # of columns       | field_columns | List (text)                | yes      | 1           |
| Section CTA / Link | field_cta     | Link                       | no       | 1           |
| Statistics Items   | field_items   | Entity reference revisions | no       | unlimited   |

### Statistics Item

**Machine name:** `statistics_item`

| Label        | Machine Name      | Type         | Required | Cardinality | Help text | Field Settings | Notes |
|--------------|-------------------|--------------|----------|-------------|-----------|----------------|-------|
| Number value | field_number      | Text (plain) | yes      | 1           |
| Description  | field_description | Text (plain) | no       | 1           |

## Table

- **Machine name:** `lb_table`
- **Project:** [lb_table](https://www.drupal.org/project/lb_table)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Tables Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Tables Desktop.png>)

Allows users to be able to view responsive tables within a page.

| Label            | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Section title	   | (inherit)    |
| Section subtitle | (inherit)    |
| Body             | body         | Text (formatted, long, with summary) | no       | 1           |

## Tabs

- **Machine name:** `lb_tabs`
- **Project:** [ws_lb_tabs](https://www.drupal.org/project/ws_lb_tabs)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Tabs Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Tabs Desktop.png>)

Gives users the ability to switch page views by selecting tabs across the top of the page instead of having to navigate to a new page.

| Label            | Machine Name | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|--------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Section title    | (inherit)    | 
| Section subtitle | (inherit)    | 
| Tabs             | field_tabs   | Entity reference revisions | no       | unlimited   |           | Bundle: Tab    |

### Tab

**Machine name:** `tab`

The Tab paragraph is referenced by the Tabs block.

| Label | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|-------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Title | field_title  | Text (plain)                         | yes      | 1           |
| Body  | field_body   | Text (formatted, long, with summary) | no       | 1           |

## Webform

- **Machine name:** `lb_webform`
- **Project:** [lb_webform](https://www.drupal.org/project/lb_webform)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Webforms Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Webforms Desktop.png>)

Embed an existing webform on a page.

| Label         | Machine Name  | Type    | Required | Cardinality | Help text | Field Settings | Notes |
|---------------|---------------|---------|----------|-------------|-----------|----------------|-------|
| Form title    | (inherit)     |
| Form subtitle | (inherit)     | 
| Webform       | field_webform | Webform | yes      | 1           |
