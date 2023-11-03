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
- **[User Docs & Designs](../../user-documentation/layout-builder/accordion)**

Expandable pairs of question/answer or header/section fields.

| Label          | Machine Name     | Type             | Required | Cardinality | Help text                                                                                                  | Field Settings         | Notes |
|----------------|------------------|------------------|----------|-------------|------------------------------------------------------------------------------------------------------------|------------------------|-------|
| Accordion item | field_block_item | Entity reference | no       | unlimited   |                                                                                                            | Bundle: accordion_item |
| FAQ?           | field_is_faq     | Boolean          | no       |             | If this section contains Frequently Asked Questions, check this box to output them as "structured data"... |

### Accordion Item

- **Machine name:** `accordion_item`

| Label   | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes   |
|---------|--------------|--------------------------------------|----------|-------------|-----------|----------------|---------|
| Heading | field_title  | Text (plain)                         | yes      | 1           |           |                | H4      |
| Body    | body         | Text (formatted, long, with summary) | yes      | 1           |           |                | WYSIWYG |

## Branch Amenities

- **Machine name:** `lb_branch_amenities`
- **Project:** [lb_branch_amenities_blocks](https://www.drupal.org/project/lb_branch_amenities_blocks)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Branch Amenities Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Branch Amenities Desktop.png>)

Display of all amenities available at a branch location.

| Label              | Machine Name | Type             | Required | Cardinality | Help text | Field Settings | Notes    |
|--------------------|--------------|------------------|----------|-------------|-----------|----------------|----------|
| Section heading    | (inherit)    |                  |          |             |           |                | H2       |
| Section subheading | (inherit)    |                  |          |             |           |                | H3       |
| Amenity name       | Text (plain) | Entity reference | yes      | unlimited   |           |                | Taxonomy |

## Cards

- **Machine name:** `lb_cards`
- **Project:** [lb_cards](https://www.drupal.org/project/lb_cards)
- **[User Docs & Designs](../../user-documentation/layout-builder/cards)**

Flexible card-style components that allow up to 4 cards to display across a page depending on the chosen layout.

| Label              | Machine Name     | Type             | Required | Cardinality | Help text | Field Settings    | Notes |
|--------------------|------------------|------------------|----------|-------------|-----------|-------------------|-------|
| Section heading    | (inherit)        |                  |          |             |           |                   | H2    |
| Section subheading | (inherit)        |                  |          |             |           |                   | H3    |
| Section link       | field_cta        | Link             | no       | 1           |
| # of columns       | field_columns    | List (text)      | yes      | 1           |           |
| Card items         | field_block_item | Entity reference | no       | 4           |           | Bundle: card_item |

### Card Item

**Machine name:** `card_item`

The Card item block is referenced by the Cards block.

| Label       | Machine Name    | Type               | Required | Cardinality | Help text | Field Settings                       | Notes |
|-------------|-----------------|--------------------|----------|-------------|-----------|--------------------------------------|-------|
| Heading     | field_title     | Text (plain)       | yes      | 1           |           |                                      | H4    |
| Image       | field_media     | Entity reference   | no       | 1           |
| Topic tag   | field_topic_tag | Entity reference   | no       | 1           |           | Bundle: blog_category, news_category |       |
| Description | field_body      | Text (plain, long) | no       | 1           |
| Link        | field_cta       | Link               | no       | 1           |

## Carousel

- **Machine name:** `lb_carousel`
- **Project:** [lb_carousel](https://www.drupal.org/project/lb_carousel)
- **[User Docs & Designs](../../user-documentation/layout-builder/carousel)**

A full-width display with multiple sets of a header, description, and call to action overlaid on top of an image.

| Label              | Machine Name     | Type             | Required | Cardinality | Help text | Field Settings        | Notes |
|--------------------|------------------|------------------|----------|-------------|-----------|-----------------------|-------|
| Section heading    | (inherit)        |                  |          |             |           |                       | H2    |
| Section subheading | (inherit)        |                  |          |             |           |                       | H3    |
| Carousel items     | field_block_item | Entity reference | no       | 6           |           | Bundle: carousel_item |

### Carousel Item

**Machine name:** `carousel_item`

| Label       | Machine Name      | Type                   | Required | Cardinality | Help text | Field Settings | Notes |
|-------------|-------------------|------------------------|----------|-------------|-----------|----------------|-------|
| Heading     | field_title       | Text (plain)           | no       | 1           |           |                | H4    |
| Image       | field_media       | Entity reference       | yes      | 1           |
| Description | field_description | Text (formatted, long) | no       | 1           |
| Link        | field_cta         | Link                   | no       | 1           |

## Code

- **Machine name:** `ws_code_block`
- **Project:** [ws_code_block](https://www.drupal.org/project/ws_code_block)
- **Designs:** This block provides no additional presentation outside of the embedded content.

Embed unfiltered HTML code in a page.

| Label | Machine Name | Type                   | Required | Cardinality | Help text | Field Settings      | Notes |
|-------|--------------|------------------------|----------|-------------|-----------|---------------------|-------|
| Code  | field_code   | Text (formatted, long) | yes      | 1           |           | Text format: "Code" |       |

## Grid CTA

- **Machine name:** `lb_grid_cta`
- **Project:** [lb_grid_cta](https://www.drupal.org/project/lb_grid_cta)
- **[User Docs & Designs](../../user-documentation/layout-builder/grid-cta)**

Sets of content with a headline, description, and link displayed in 2 to 4-item wide rows, with the option to include icons or images.

| Label               | Machine Name           | Type             | Required | Cardinality | Help text                                            | Field Settings    | Notes                              |
|---------------------|------------------------|------------------|----------|-------------|------------------------------------------------------|-------------------|------------------------------------|
| Section heading     | (inherit)              |                  |          |             |                                                      |                   | H2                                 |
| Section subheading  | (inherit)              |                  |          |             |                                                      |                   | H3                                 |
| Grid CTA section link | field_section_cta_link | Link             | no       | 1           | A link button to be displayed below the grid content |
| # of columns        | field_columns          | List (text)      | yes      | 1           |                                                      |                   | Allows 2-4 columns, defaults to 4. |
| Grid item        | field_block_item       | Entity Reference | yes      | 4           |                                                      | Bundle: grid_item |

### Grid Item

**Machine name:** `grid_item`

The Grid Item block is referenced by the Grid CTA component.

| Label       | Machine Name      | Type                   | Required | Cardinality | Help text | Field Settings | Notes |
|-------------|-------------------|------------------------|----------|-------------|-----------|----------------|-------|
| Heading     | field_title       | Text (plain)           | no       | 1           |           |                | H4    |
| Description | field_description | Text (formatted, long) | no       | 1           |
| Media       | field_media       | Entity reference       | no       | 1           |
| Link        | field_cta         | Link                   | no       | 1           |

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
| Link    | field_link    | Link                   | no       | 1           |

## Partners

- **Machine name:** `lb_partners`
- **Project:** [lb_partners_blocks](https://www.drupal.org/project/lb_partners_blocks)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Sponsors Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Sponsors Desktop.png>)

List of multiple partner / sponsor logos.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading    | (inherit)     |  |  |  |  |  | H2 |
| Section subheading  | (inherit)     |  |  |  |  |  | H3 |
| Partner items | field_partner_items | Entity reference revisions | no | unlimited? |  | Bundle: lb_partner_item |

### Partner Item

**Machine Name:** `lb_partner_item`
| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Heading | field_item_heading | Text (plain)  | Yes |  |  |  | H4 |
| Image | field_item_image | Entity reference | Yes |


## Ping-pong

- **Machine name:** `lb_ping_pong`
- **Project:** [lb_ping_pong](https://www.drupal.org/project/lb_ping_pong)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Ping Pong Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Ping Pong Desktop.png>)

Usually paired sets of full-width page components that include media, header, description, and call to action arranged horizontally.

| Label               | Machine Name              | Type                   | Required | Cardinality | Help text                                                                                                          | Field Settings | Notes |
|---------------------|---------------------------|------------------------|----------|-------------|--------------------------------------------------------------------------------------------------------------------|----------------|-------|
| Section heading   | (inherit)            |               |  |  |  |  | H2 |
| Section subheading      |  (inherit)              |              |  |  |  |  | H3 |
| Heading          | field_item_heading          | Text (plain)           | no       | 1           |  |  | H4 |
| Description    | field_item_description    | Text (formatted, long) | no       | 1           |  |  | WYSIWYG |
| Link       | field_item_link            | Link                   | no       | 2           | The first will use the primary style and the second, secondary.                                                    |
| Image          | field_item_image          | Entity reference       | no       | 1           |
| Image position | field_item_image_position | List (text)            | yes      | 1           | Places the image on this side of the page in the full-width display. Image will stack above text at narrow widths. |


## Promo Card

- **Machine name:** `lb_promo`
- **Project:** [lb_promo](https://www.drupal.org/project/lb_promo)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Promo Cards Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Promo Cards Desktop.png>)

A title, headline, description, and link that usually display in the right or left sidebar.

| Label        | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|--------------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Title        | field_title  | Text (plain)                         | yes      | 1           |
| Body         | body         | Text (formatted, long, with summary) | no       | 1           |  |  |
| Image | field_image  | Entity reference                     | no       | 1           |           | Bundle: Image  |
| Link   | field_link    | Link                                 | no       | 1           |

## Related Articles

- **Machine name:** `lb_related_articles`
- **Project:** [lb_related_articles_blocks](https://www.drupal.org/project/lb_related_articles_blocks)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Article Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Article Desktop.png>)

Component for displaying related articles within a page.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading     | (inherit)     |  |  |  |  |  | H2 |
| Section subheading  | (inherit)     |  |  |  |  |  | H3 |

## Related Events

- **Machine name:** `lb_related_events`
- **Project:** [lb_related_events_blocks](https://www.drupal.org/project/lb_related_events_blocks)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Events Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Event Desktop.png>)

Component for displaying related events within a page.

| Label              | Machine Name | Type | Required | Cardinality | Help text | Field Settings | Notes |
|--------------------|--------------|------|----------|-------------|-----------|----------------|-------|
| Section heading    | (inherit)    |      |          |             |           |                | H2    |
| Section subheading | (inherit)    |      |          |             |           |                | H3    |

## Simple Content

- **Machine name:** `lb_simple_content`
- **Project:** [lb_simple_content]()
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Tables Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Tables Desktop.png>)

Allows users to be able to view responsive tables within a page.

| Label            | Machine Name | Type                                 | Required | Cardinality | Help text | Field Settings | Notes |
|------------------|--------------|--------------------------------------|----------|-------------|-----------|----------------|-------|
| Section heading	   | (inherit)    |  |  |  |  |  | H2 |
| Section subheading | (inherit)    |  |  |  |  |  | H3 |
| Body             | body         | Text (formatted, long, with summary) | no       | 1           |  |  | Allows for responsive tables to be placed in the body. |

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
- **Project:** [lb_staff_members_blocks](https://www.drupal.org/project/lb_staff_members_blocks)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Staff Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Staff Desktop.png>)

Displays simple staff member info cards with image, name, title, email

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading     | (inherit)     |  |  |  |  |  | H2 |
| Section subheading  | (inherit)     |  |  |  |  |  | H3 |
| Staff items | field_staff_items | Entity reference revisions | no | unlimited? |  | Bundle: lb_staff_item |

### Staff Item

**Machine name:** `lb_staff_item`

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Name | field_item_name | Text (plain) | Yes | 1 |  |  | H4 |
| Image | field_item_image | Entity reference | Yes | 1 |  |  | If no image uploaded, utilize default |
| Job title | field_item_job_title | Text (plain) | Yes | 1 |
| Email | field_item_email | Text (formatted, mailto) | Yes | 1 |  |  | Clicking on email should open users default email client |

## Statistics

- **Machine name:** `lb_statistics`
- **Project:** [lb_statistics](https://www.drupal.org/project/lb_statistics)
- **[User Docs & Designs](../../user-documentation/layout-builder/statistics)**

Infographic-like display that highlights relevant statistics to users.

| Label             | Machine Name     | Type                      | Required | Cardinality | Help text | Field Settings          | Notes |
|-------------------|------------------|---------------------------|----------|-------------|-----------|-------------------------|-------|
| Section heading   | (inherit)        |                           |          |             |           |                         | H2    |
| Section subheading | (inherit)        |                           |          |             |           |                         | H3    |
| # of columns      | field_columns    | List (text)               | yes      | 1           |           |                         |       |
| Section link      | field_cta        | Link                      | no       | 1           |           |                         |       |
| Statistics item   | field_block_item | Entity reference | no       | unlimited   |           | Bundle: statistics_item |       |

### Statistics Item

**Machine name:** `statistics_item`

| Label        | Machine Name      | Type         | Required | Cardinality | Help text | Field Settings | Notes |
|--------------|-------------------|--------------|----------|-------------|-----------|----------------|-------|
| Number value | field_subtitle    | Text (plain) | yes      | 1           |
| Description  | field_description | Text (plain) | no       | 1           |

## Tabs

- **Machine name:** `lb_tabs`
- **Project:** [ws_lb_tabs](https://www.drupal.org/project/ws_lb_tabs)
- **[User Docs & Designs](../../user-documentation/layout-builder/tabs)**

Gives users the ability to switch page views by selecting tabs across the top of the page instead of having to navigate to a new page.

| Label              | Machine Name      | Type             | Required | Cardinality | Help text | Field Settings   | Notes |
|--------------------|-------------------|------------------|----------|-------------|-----------|------------------|-------|
| Section heading    | (inherit)         |                  |          |             |           |                  | H2    |
| Section subheading | (inherit)         |                  |          |             |           |                  | H3    |
| Tab item           | 	field_block_item | Entity reference | no       | unlimited   |           | Bundle: tab_item |

### Tab Item

**Machine name:** `tab_item`

The Tab Item block is referenced by the Tabs block.

| Label   | Machine Name      | Type                   | Required | Cardinality | Help text | Field Settings | Notes   |
|---------|-------------------|------------------------|----------|-------------|-----------|----------------|---------|
| Heading | field_heading     | Text (plain)           | yes      | 1           |           |                | H4      |
| Body    | field_description | Text (formatted, long) | no       | 1           |           |                | WYSIWYG |


## Testimonials

- **Machine name:** `lb_testimonials`
- **Project:** [lb_testimonial_blocks](https://www.drupal.org/project/lb_testimonial_blocks)
- **Designs:** [Mobile](<../../../../../assets/img/designs/lb/Testimonials Mobile.png>) | [Desktop](<../../../../../assets/img/designs/lb/Testimonials Desktop.png>)

Display of short testimonials or quotes from Y members.

| Label          | Machine Name                     | Type                       | Required | Cardinality | Help text | Field Settings         | Notes |
|----------------|----------------------------------|----------------------------|----------|-------------|-----------|------------------------|-------|
| Section heading    | (inherit)     |  |  |  |  |  | H2 |
| Section subheading | (inherit)     |  |  |  |  |  | H3 |
| Testimonial items | field_testimonial_items | Entity reference revisions | no | 4 |  | Bundle: lb_testimonial_item |

### Testimonial Item

**Machine Name:** `lb_testimonial_item`

| Label | Machine Name     | Type             | Required | Cardinality | Help text | Field Settings      | Notes                                 |
|-------|------------------|------------------|----------|-------------|-----------|---------------------|---------------------------------------|
| Name  | field_item_name  | Text (plain)     | Yes      | 1           |           | Firstname, Lastname | H4                                    |
| Image | field_item_image | Entity reference | Yes      | 1           |           |                     | If no image uploaded, utilize default |
| Quote | field_item_quote | Text (plain)     | Yes      | 1           |           |                     |                                       |

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
