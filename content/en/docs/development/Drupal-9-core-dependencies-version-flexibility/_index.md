---
title: Drupal 9 core dependencies version flexibility
aliases:
  - /docs/wiki/drupal-9-core-dependencies-version-flexibility/
---

This document is no longer updated.

To update the version of Drupal being used on your site independent of YMCA Website Services see [Updating Drupal Core via Composer](https://www.drupal.org/docs/updating-drupal/updating-drupal-core-via-composer). Be aware that `openy/composer.json` may set [Drupal core version constraints](https://github.com/YCloudYUSA/yusaopeny/blob/9.x-2.x/composer.json#:~:text=%22drupal/-,core%2Drecommended,-%22%3A%20%22%3E%3D9.1%2C%20%3C9.3%22%2C).

----

February 2021 release tagged Drupal core both 9.0.x and 9.1.x as allowed to be used.

Composer by default is installing the latest stable version, so a command

```bash
composer create-project YCloudYUSA/yusaopeny-project:dev-9.2.x-development OPENY --no-interaction
```

will install YMCA Website Services on latest 9.1.x Drupal core.

If there is a need to stay on Drupal 9.0.x stable core please use

```bash
composer create-project YCloudYUSA/yusaopeny-project:dev-9.2.x-development OPENY --no-interaction
cd OPENY
composer require drupal/core:~9.0.7
```

where 9.0.7 - is a needed version for your YMCA Website Services instance

For modules see [Composer-version-constraints-for-Open-Y]({{< relref "Composer-version-constraints-for-Open-Y.md" >}})
