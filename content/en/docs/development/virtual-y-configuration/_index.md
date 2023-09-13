---
title: Virtual Y Configuration
aliases:
  - /docs/wiki/virtual-y-configuration/
---

## Virtual Y predefined pages

Once Virtual Y installed system creates set of required Landing pages with predefined URLs. These pages are:
* Virtual Y Landing page - `/virtual-ymca`
* Virtual Y Login Landing page - `/virtual-y-login`

URLs to pages above then set as configuration values at `/admin/openy/virtual-ymca`. 

Admin user is obligated to keep pages in the system or properly update configuration with new values to keep Virtual Y functionality working correctly. 

## Protecting Virtual Y Pages

If content editors modify the alias or remove the Virtual Y pages above, the VY site may break. Site administrators may want to add additional protections to the site to prevent editors from making those changes. We recommend [Node Keep](https://www.drupal.org/project/node_keep) for this purpose:

- Add `node_keep` to your repo with `composer require 'drupal/node_keep'
- Enable the module in Drupal
- Edit each of the pages above and set the Node Keep options as you wish to protect the pages

![Screenshot displaying Node Keep options](./vy-node-keep.png)

## Virtual Y Log module

Virtual Y Log module can be configured via configuration files. Available settings:

* `activity_granularity_interval`: Default value `600` - sets the interval in Seconds to track user activity on the site
* `archiver_enabled`: default value `true` - enable / disable activity logs archiver cron execution
* `archiver_store_period`: default value `1 year` - set the period when activity logs will be collected and placed to same archive. This value should be set to as Relative Date/Time PHP string, e.g. `1 week`, `2 months`, `1 year`, etc.
