---
title: Composer version constraints for YMCA Website Services
aliases:
  - /docs/wiki/composer-version-constraints-for-open-y/
---

In 2020, due to changes in Drupal core release management and demand from YMCA Website Services customers to improve upgrade path flexibility and stability, the YMCA Website Services team added extended composer version constraints to our `composer.json`.

Examples from [composer.json](https://github.com/YCloudYUSA/yusaopeny/blob/9.x-2.x/composer.json):

- `"drupal/ckeditor_bootstrap_buttons": "^1.2 || ^2.0.0",` - this line means previous version was 1.2 or any 1.x starting from 1.2, and latest tested - 2.0.0 with allowed any stable 2.x starting from 2.0.0
- `"drupal/custom_formatters": "^3.0 || ^3.0@beta",` - tested with 3.0 beta of custom_formatters and allowed any 3.x starting from 3.0 (when it will be released)

By having multiple OR (`||`) conditions we are providing information for developers on which versions could be used for upgrades. There are cases when the latest, even stable version of dependency could be incompatible with some other functionality and it makes sense to keep the version older while functionality is in the process of upgrading.

For example, if, for some reason, `custom_formatters` 3.0 won't be compatible with any of YMCA Website Services dependencies at the time of release, a developer can select an older beta version in order to proceed with the upgrade.

To select a specific version of a dependency when you do an upgrade of YMCA Website Services, add a dependency and its version alongside YMCA Website Services at the `composer require...` step.

For example:

from [upgrade doc]({{< relref "OpenY-upgrade-how-to-for-Developers" >}})

```bash
composer require YCloudYUSA/yusaopeny:NEW_VERSION_HERE --no-update
composer update --prefer-dist --with-dependencies --prefer-stable --no-suggest
```

then change the dependency version

```bash
composer require YCloudYUSA/yusaopeny:NEW_VERSION_HERE --no-update
composer require drupal/custom_formatters:3.0@beta1
```

You can change any of the dependency versions without upgrading YMCA Website Services by running only the `composer require...` command for specific dependencies and Drupal Update DB routines afterward.

Check [official Composer documentation about version constraints](https://getcomposer.org/doc/articles/versions.md) and [updating Drupal modules with Composer](https://www.drupal.org/docs/updating-drupal/updating-modules-and-themes-using-composer).
