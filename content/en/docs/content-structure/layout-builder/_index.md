---
title: Layout Builder
---

These custom block types exist to support page building with Layout Builder.

## Global Fields

These fields are reused across many of the below components.

| Label            | Machine Name           | Type               | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|------------------------|--------------------|----------|-------------|-----------|----------------|-------|
| Section heading     | field_section_heading    | Text (plain)       | no       | 1           |  |  | H2 |
| Section subheading  | field_section_subheading | Text (plain, long) | no       | 1           |  |  | H3 |

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
| Heading  | field_heading  | Text (plain)                         | yes      | 1           |  |  | H4 |
| Body  | field_body   | Text (formatted, long, with summary) | no       | 1           |  |  | WYSIWYG |

## Branch Amenities

- **Machine name:** `lb_branch_amenities`
- **Project:** [lb_branch_amenities]
- **Designs:** [Mobile](<>) | [Desktop](<>)

Display of all amenities available at a branch location.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading     | (inherit)     |  |  |  |  |  | H2
| Section subheading  | (inherit)     |  |  |  |  |  | H3
| Amenity name | Text (plain) | Entity reference (amenities taxonomy?) | yes | unlimited |  |  | Taxonomy? |

## Cards

- **Machine name:** `lb_cards`
- **Project:** [lb_cards](https://www.drupal.org/project/lb_cards)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Cards Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Cards Mobile.png>)

Flexible card-style components that allow up to 4 cards to display across a page depending on the chosen layout.

| Label            | Machine Name  | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|---------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Section heading    | (inherit)     |  |  |  |  |  | H2 |
| Section subheading | (inherit)     |  |  |  |  |  | H3 |
| Section CTA / Link | field_section_link     | Link                       | no       | 1           |
| # of columns     | field_section_columns | List (text)                | yes      | 1           |           | 
| Card Item            | field_card_item   | Entity reference revisions | no       | 4           |           | Bundle: card_item  |

### Card Item

**Machine name:** `lb_card_item`

The Card paragraph is referenced by the Cards block.

| Label       | Machine Name           | Type               | Required | Cardinality | Help text | Field Settings | Notes                   |
|-------------|------------------------|--------------------|----------|-------------|-----------|----------------|-------------------------|
| Heading       | field_item_heading       | Text (plain)       | yes      | 1           |  |  | H4 |
| Image       | field_item_image       | Entity reference   | no       | 1           |
| Topic Tag   | field_item_topic_tag   | Text (plain)       | no       | 1           |           |                | May be changed to term. |
| Description | field_item_description | Text (plain, long) | no       | 1           |
| CTA / Link    | field_item_link         | Link               | no       | 1           |

## Carousel

- **Machine name:** `lb_carousel`
- **Project:** [lb_carousel](https://www.drupal.org/project/lb_carousel)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Carousels Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Carousels Desktop.png>)

A full-width display with multiple sets of a header, description, and call to action overlaid on top of an image.

| Label             | Machine Name         | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|-------------------|----------------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Section heading     | (inherit)  |                |        |            |  |  | H2 |
| Section subheading | (inherit)       |                |        |            |  |  | H3 |
| Carousel Items    | field_carousel_item | Entity reference revisions | no       | 6   |  | Bundle: carousel_item | 

### Carousel Item

**Machine name:** `lb_carousel_item`

| Label       | Machine Name               | Type                   | Required | Cardinality | Help text | Field Settings | Notes |
|-------------|----------------------------|------------------------|----------|-------------|-----------|----------------|-------|
| Heading       | field_item_heading                | Text (plain)           | no       | 1           |  |  | H4 |
| Image       | field_item_image       | Entity reference       | no       | 1           |
| Description | field_item_description | Text (formatted, long) | no       | 1           |
| CTA \ Link  | field_item_link         | Link                   | no       | 1           |

## Grid CTA

- **Machine name:** `lb_grid_cta`
- **Project:** [lb_grid_cta](https://www.drupal.org/project/lb_grid_cta)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Grid Content Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Grid Content Desktop.png>)

Sets of content with a headline, description, and link displayed in 2 to 4-item wide rows, with the option to include icons or images.

| Label                 | Machine Name                | Type             | Required | Cardinality | Help text                                            | Field Settings    | Notes                              |
|-----------------------|-----------------------------|------------------|----------|-------------|------------------------------------------------------|-------------------|------------------------------------|
| Section heading         | (inherit)                   |  |  |  |  |  | H2 |
| Section subheading     | (inherit)                   |  |  |  |  |  | H3 |
| Grid section CTA / link | field_section_link | Link             | no       | 1           | A link button to be displayed below the grid content |
| # of columns          | field_section_columns               | List (text)      | yes      | 1           |                                                      |                   | Allows 2-4 columns, defaults to 4. |
| Grid Items            | field_grid__cta_item            | Entity Reference | yes      | 4   |                                                      | Bundle: grid_cta_item |

### Grid CTA Item

**Machine name:** `lb_grid_cta_item`

The Grid Item paragraph is referenced by the Grid CTA component.

| Label                 | Machine Name                | Type                   | Required | Cardinality | Help text | Field Settings | Notes |
|-----------------------|-----------------------------|------------------------|----------|-------------|-----------|----------------|-------|
| Heading       | field_item_heading       | Text (plain)           | no       | 1           |  |  | H4 |
| Description | field_item_description | Text (formatted, long) | no       | 1           |
| Media       | field_item_icon        | Entity reference       | no       | 1           |
| CTA / Link    | field_item_link    | Link                   | no       | 1           |

## Hero Banner

- **Machine name:** `lb_hero`
- **Project:** [lb_hero](https://www.drupal.org/project/lb_hero)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Hero Banner Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Hero Banner Desktop.png>)

A full-width, almost full-height display with a header, description, and call to action overlaid on an image.

| Label       | Machine Name      | Type                   | Required | Cardinality | Help text | Field Settings                    | Notes |
|-------------|-------------------|------------------------|----------|-------------|-----------|-----------------------------------|-------|
| Heading       | field_heading       | Text (plain)           | yes      | 1           |  |  | H2 |
| Description | field_description | Text (formatted, long) | no       | 1           | 
| Media       | field_media       | Entity reference       | no       | 1           |           | Bundle: Image, Local Video, Video |
| CTA \ Link    | field_link    | Link                   | no       | 1           |

## Partners

- **Machine name:** `lb_partners`
- **Project:** [lb_partners]
- **Designs:** [Mobile](<>) | [Desktop](<>)

List of multiple partner / sponsor logos.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading    | (inherit)     |  |  |  |  |  | H2 |
| Section subheading  | (inherit)     |  |  |  |  |  | H3 |
| Partner Items | field_partner_item | Entity reference revisions | no | unlimited? |  | Bundle: partner_item | 
### Partner Item

**Machine Name:** `lb_partner_item`
| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Heading | field_item_heading | Text (plain)  | Yes |  |  |  | H4 |
| Logo / Image | field_item_image | Entity reference | No | 


## Ping-pong

- **Machine name:** `lb_ping_pong`
- **Project:** [lb_ping_pong](https://www.drupal.org/project/lb_ping_pong)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Ping Pong Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Ping Pong Desktop.png>)

Usually paired sets of full-width page components that include media, header, description, and call to action arranged horizontally.

| Label               | Machine Name              | Type                   | Required | Cardinality | Help text                                                                                                          | Field Settings | Notes |
|---------------------|---------------------------|------------------------|----------|-------------|--------------------------------------------------------------------------------------------------------------------|----------------|-------|
| Section Heading   | (inherit)            |               |  |  |  |  | H2 |
| Section Subheading      |  (inherit)              |              |  |  |  |  | H3 |
| Heading          | field_item_heading          | Text (plain)           | no       | 1           |  |  | H4 |
| Description    | field_item_description    | Text (formatted, long) | no       | 1           |  |  | WYSIWYG |
| CTA \ Link       | field_item_link            | Link                   | no       | 2           | The first will use the primary style and the second, secondary.                                                    |
| Image          | field_item_image          | Entity reference       | no       | 1           |
| Image Position | field_item_image_position | List (text)            | yes      | 1           | Places the image on this side of the page in the full-width display. Image will stack above text at narrow widths. |


## Promo Card

- **Machine name:** `lb_promo`
- **Project:** [lb_promo](https://www.drupal.org/project/lb_promo)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Promo Cards Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Promo Cards Desktop.png>)

A title, headline, description, and link that usually display in the right or left sidebar.

| Label        | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|--------------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Title        | field_title  | Text (plain)                         | yes      | 1           |
| Body         | field_body         | Text (formatted, long, with summary) | no       | 1           |  |  | 
| Icon / Image | field_image  | Entity reference                     | no       | 1           |           | Bundle: Image  |
| CTA / Link   | field_link    | Link                                 | no       | 1           |

## Related Articles

- **Machine name:** `lb_related_articles`
- **Project:** [lb_related_articles](<>)
- **Designs:** [Mobile](<>) | [Desktop](<>)

Component for displaying related articles within a page.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading     | (inherit)     |  |  |  |  |  | H2 |
| Section subheading  | (inherit)     |  |  |  |  |  | H3 |

## Related Events

- **Machine name:** `lb_related_events`
- **Project:** [lb_related_events](<>)
- **Designs:** [Mobile](<>) | [Desktop](<>)

Component for displaying related events within a page.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading     | (inherit)     |  |  |  |  |  | H2 |
| Section subheading  | (inherit)     |  |  |  |  |  | H3

## Simple Menu

- **Machine name:** `lb_simple_menu`
- **Project:** [lb_simple_menu](https://www.drupal.org/project/lb_simple_menu)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Simple Menu Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Simple Menu Desktop.png>)

A simple 1-level sidebar menu that can display in either the right or left sidebar area.

| Label | Machine Name               | Type             | Required | Cardinality | Help text | Field Settings | Notes |
|-------|----------------------------|------------------|----------|-------------|-----------|----------------|-------|
| Icon  | field_icon                 | Entity reference | no       | 1           |           | Bundle: Image  |
| Links | field_links | Link             | yes      | unlimited   |

## Staff

- **Machine name:** `lb_staff`
- **Project:** [lb_staff](<>)
- **Designs:** [Mobile](<>) | [Desktop](<>)

Displays simple staff member info cards with image, name, title, email

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading     | (inherit)     |  |  |  |  |  | H2 |
| Section subheading  | (inherit)     |  |  |  |  |  | H3 |
| Staff | field_staff_item | Entity reference revisions | no | unlimited? |  | Bundle: staff_items |

### Staff Item

**Machine name:** `lb_staff_item`

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Name | field_item_name | Text (plain) | Yes | 1 |  | Firstname, Lastname | H4 |
| Image | field_item_image | Entity reference | No | 1 |  |  | If no image uploaded, utilize default |
| Title | field_item_title | Text (plain) | Yes | 1 | 
| Email | field_item_email | Text (formatted, mailto) | Yes | 1 |  |  | Clicking on email should open users default email client |

## Statistics

- **Machine name:** `lb_statistics`
- **Project:** [lb_statistics](https://www.drupal.org/project/lb_statistics)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Statistics Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Statistics Desktop.png>)

Infographic-like display that highlights relevant statistics to users.

| Label              | Machine Name  | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|--------------------|---------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Section heading       | (inherit)     |  |  |  |  |  | H2 |
| Section subheading    | (inherit)     |  |  |  |  |  | H3 |
| # of columns       | field_columns | List (text)                | yes      | 1           |
| Section CTA / Link | field_link     | Link                       | no       | 1           |
| Statistics Items   | field_statistics_ items   | Entity reference revisions | no       | unlimited   |

### Statistics Item

**Machine name:** `lb_statistics_item`

| Label        | Machine Name      | Type         | Required | Cardinality | Help text | Field Settings | Notes |
|--------------|-------------------|--------------|----------|-------------|-----------|----------------|-------|
| Number value | field_item_number      | Text (plain) | yes      | 1           |
| Description  | field_item_description | Text (plain) | no       | 1           |

## Tabs

- **Machine name:** `lb_tabs`
- **Project:** [ws_lb_tabs](https://www.drupal.org/project/ws_lb_tabs)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Tabs Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Tabs Desktop.png>)

Gives users the ability to switch page views by selecting tabs across the top of the page instead of having to navigate to a new page.

| Label            | Machine Name | Type                       | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|--------------|----------------------------|----------|-------------|-----------|----------------|-------|
| Section heading   | (inherit)    |  |  |  |  |  | H2 |
| Section subheading | (inherit)    |  |  |  |  |  | H3 |
| Tab Items             | field_tab_items   | Entity reference revisions | no       | unlimited   |           | Bundle: tab_item    |

### Tab Item

**Machine name:** `lb_tab_item`

The Tab paragraph is referenced by the Tabs block.

| Label | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|-------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Heading | field_heading  | Text (plain)                         | yes      | 1           |  |  | H4 |
| Body  | field_body   | Text (formatted, long, with summary) | no       | 1           |  |  | WYSIWYG |

## Table

- **Machine name:** `lb_table`
- **Project:** [lb_table](https://www.drupal.org/project/lb_table)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Tables Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Tables Desktop.png>)

Allows users to be able to view responsive tables within a page.

| Label            | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Section heading	   | (inherit)    |  |  |  |  |  | H2 |
| Section subheading | (inherit)    |  |  |  |  |  | H3 |
| Body             | field_body         | Text (formatted, long, with summary) | no       | 1           |

## Testimonials

- **Machine name:** `lb_testimonials`
- **Project:** [lb_testimonial]
- **Designs:** [Mobile](<>) | [Desktop](<>)

Display of short testimonials or quotes from Y members.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading    | (inherit)     |  |  |  |  |  | H2 |
| Section subheading | (inherit)     |  |  |  |  |  | H3 |
| Testimonials | field_testimonial_item | Entity reference revisions | no | 4 |  | Bundle: testimonial_item | 

### Testimonial Item

**Machine Name:** `lb_testimonial_item`

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Name | field_item_name | Text (plain) | Yes | 1 |  | Firstname, Lastname | H4 |
| Image | field_item_image | Entity reference | no | 1 |  |  | If no image uploaded, utilize default
| Quote | field_item_quote | Text (plain) | Yes | 1 | 

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
