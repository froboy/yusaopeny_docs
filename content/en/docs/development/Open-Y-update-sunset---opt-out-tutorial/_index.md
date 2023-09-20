---
title: Open Y analytics sunset
aliases:
  - /docs/wiki/open-y-update-sunset---opt-out-tutorial/
---

## Preamble

Back on 28 Jan 2020 Open Y decided to add an anonymous analytics module [`openy_analytics`](https://github.com/YCloudYUSA/yusaopeny/tree/9.x-2.x/modules/custom/openy_analytics) which was a free opt-in/opt-out solution for the Core team to gather stats from Open Y sites about the frequency of components used.

The idea behind this was to gather data in order to understand the demand for the components in Open Y and use the data to make better decisions.

Recently, the Open Y Core Team decided to sunset this functionality and remove `openy_analytics` as well as `openy_update` modules from the Open Y Distribution, as this feature was rarely used. By sunsetting this functionality, we reduced server load from Open Y instances and archive the analytics server.

## How to opt-out from analytics subsystem

Visit YMCA Website Services -> Terms and Conditions in your YMCA Website Services site instance and uncheck the Optional Permissions checkbox

![image](https://user-images.githubusercontent.com/563412/130236284-5979a4fe-289c-4ccc-9c18-059d17d143e8.png)

After submitting this form your site will stop sending anonymous data.

If the checkbox was not enabled just disregard it, you didn't opt-in earlier.

## Deprecation action

Uninstall and deprecation was done in [#2537](https://github.com/YCloudYUSA/yusaopeny/pull/2537)
