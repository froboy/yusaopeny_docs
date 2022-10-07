---
title: Virtual Y Configuration
---

# Virtual Y predefined pages

Once Virtual Y installed system creates set of required Landing pages with predefined URLs. These pages are:
* Virtual Y Landing page - `/virtual-ymca`
* Virtual Y Login Landing page - `/virtual-y-login`

URLs to pages above then set as configuration values at `/admin/openy/virtual-ymca`. 

Admin user is obligated to keep pages in the system or properly update configuration with new values to keep Virtual Y functionality working correctly. 


# Virtual Y Log module

Virtual Y Log module can be configured via configuration files. Available settings:

* `activity_granularity_interval`: Default value `600` - sets the interval in Seconds to track user activity on the site
* `archiver_enabled`: default value `true` - enable / disable activity logs archiver cron execution
* `archiver_store_period`: default value `1 year` - set the period when activity logs will be collected and placed to same archive. This value should be set to as Relative Date/Time PHP string, e.g. `1 week`, `2 months`, `1 year`, etc.
