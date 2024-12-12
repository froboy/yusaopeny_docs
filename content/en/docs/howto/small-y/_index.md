---
title: "How to set up a site with the Small Y template"
linkTitle: "set up a Small Y site"
description: The Small Y template is a set of modules and themes tailored to the needs of Small YMCAs.
---

## What is the Small Y template?

The Small Y template is a set of modules and themes tailored to the needs of Small YMCAs. It is designed to be a lightweight, easy-to-use solution for small organizations that need a simple, effective website.

A full working sandbox of the Small Y template is available at [https://small-y-stable.y.org/demo-ui-kit](https://small-y-stable.y.org/demo-ui-kit).

### What's different?

#### New, simplified theme

The Small Y template includes updates to the Layout Builder design system provided by VML in collaboration with the YMCA of the USA. View a [mockup of the new theme (Figma)](https://www.figma.com/proto/yjxiX0VDNIeyefeDcuOWkS/YMCA_Small-Y-Template_Design-System?node-id=185-2300&node-type=canvas&t=ON1Hn9VBB4YT6xuQ-1&scaling=min-zoom&content-scaling=fixed&page-id=185%3A2299).

#### Only the most essential modules

The Small Y template is built with a small set of modules that are essential for a basic YMCA website. This makes it easier to set up and maintain, and reduces the weight of the site.

Modules and features included with the Small Y template include:

- Updated header and footer
- [Layout Builder](../../user-documentation/layout-builder)
- [Articles](../../user-documentation/content-types/lb-article)
- [Events](../../user-documentation/content-types/lb-event)
- [Branches](../../user-documentation/content-types/branch)
- [Camps](../../user-documentation/content-types/camp)
- [CKEditor 5 Text Editor](../../user-documentation/text-editor)

Any other modules or features of the distribution can be added as needed via the Drupal admin interface.

## Install the Small Y template

The Small Y template can be installed via the YMCA Website Services Installation wizard or the command line.

- **Installation Wizard**: The YMCA Website Services Installation wizard is a web-based tool that guides you through the process of setting up a new YMCA website. It includes a step-by-step process for configuring the site.
  - When asked to choose the Installation Type, choose "Small Y" and proceed with the installation steps.
- **Command line**
  - `drush -vy si openy openy_configure_profile.preset=small_y openy_theme_select.theme=openy_carnation openy_terms_of_use.agree_openy_terms=1 install_configure_form.enable_update_status_emails=NULL --account-name=admin --site-name='YMCA Website Services'`

