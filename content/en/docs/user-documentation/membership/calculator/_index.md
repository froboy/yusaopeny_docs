---
title: Membership Calculator
description: This simple application provides an interactive "membership wizard" with location and pricing options to attract members. It is the default membership experience.
tags:
- "Decoupled Applications"
- "Membership Calculator"
---

The Membership Calculator is bundled with the distribution in the [`openy_calc` module](https://github.com/open-y-subprojects/openy_custom/tree/main/openy_calc).

As of August 2024, the Membership Calculator has [an updated design](https://www.figma.com/design/wVbmVOI5zwOMDYRjI3GLEI/YUSA-Design-System?node-id=5095-21390&t=R5aJZuowJGTQIvNk-1) with improved functionality and user experience. The improved design will also respond to the selected [colorway and page styles](../../layout-builder/advanced-options/#page-styles).

## Configuring the Calculator

The **Membership Calculator** uses [Membership](../../content-types/membership) content items. Those will need to be created in order for the **Membership Calculator** to function.

First, create a Membership node for each membership type your Branch or Association offers. Then, inside each Membership node, add a Membership Info Paragraph with the details of that membership at each of your Locations.

The Membership Calculator is a three-step process:
1. Membership Type
2. Primary Location
3. Summary

### Membership Type

This step lists the Title, Image, and Description of each published Member node.

![A screenshot of the membership calculator Type step.](membership-calculator--type.png)

### Primary Location
This step provides a map with radio buttons for the member to select their primary location. Every location listed in the **YMCA Website Services Location Filter Settings** (see Troubleshooting section below) is listed.

![A screenshot of the membership calculator Location step.](membership-calculator--location.png)

### Summary

This page provides a link for the member to continue their registration, or a message indicating the selected membership is not provided at the selected location.

![A screenshot of the membership calculator summary step with a price listed.](membership-calculator--summary-price.png)
![A screenshot of the membership calculator summary step showing no membership available.](membership-calculator--summary-none.png)

## Placing the Calculator on a page

Once configured, the Membership Calculator can be placed on a page using:

- [Paragraphs](../../paragraphs/membership-calculator)
- [Layout Builder](../../layout-builder)

## Troubleshooting

On some sites, the second step of the *Membership Calculator* may not show any locations. In order to resolve this, visit **Administration** > **YMCA Website Services** > **Settings** > **YMCA Website Services Location Filter Settings** and ensure that any Branches you want to use in the location search are checked.

![A screenshot displaying the Location Filter settings.](membership-calculator--locations-filter.png)
