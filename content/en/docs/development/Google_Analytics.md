---
title: Google Analytics
---

## Introduction

YMCA Website Services uses the Drupal contrib [Google Analytics module](https://www.drupal.org/project/google_analytics) to enable [Google Analytics](https://marketingplatform.google.com/about/analytics/) tracking on your YMCA Website Services site.

To get started, you should first create a GA property. Use the [Analytics Help](https://support.google.com/analytics/#topic=10737980) for assistance.

## Configuration

Configuration is done at the standard module configuration page: `/admin/config/services/google-analytics`.

### Google Analytics Version Compatibility

In the [9.2.11](https://github.com/YCloudYUSA/yusaopeny/releases/tag/9.2.11) release in November 2021, YMCA Website Services [added support for Google Analytics 4](https://github.com/YCloudYUSA/yusaopeny/pull/2400). If your site has been updated to YMCA Website Services 9.2.11 or greater AND the `google_analytics` module has been updated to 4.x you should be able to use GA4. Otherwise you'll need to stick with GA3.

See this [community post](https://community.openymca.org/t/about-google-analytics-compatibility/917) for more information.
