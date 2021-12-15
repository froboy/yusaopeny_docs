Open Y development moves quickly and in this document, we flag important versions that should not be skipped while you upgrade your sites.

## Determining your upgrade path

For example: If you are on Open Y 8.1.2 and want to upgrade to Open Y 8.2.8.5 you should make it in a couple of steps

1. Upgrade 8.1.2 to 8.1.13.1
1. Upgrade 8.1.13.1 to 8.2.2.1
1. Upgrade 8.2.2.1 to 8.2.7.3
1. Upgrade 8.2.7.3 ...

These supplemental documents elaborate on a few specific cases:

- [[Upgrade from Open Y <8.1.3|OpenY-upgrade-for-developers.-Upgrade-to-old-OpenY-1.x-version]]
- [[Upgrade from 8.1.3 to 8.2.2.1|Upgrade-OpenY-8.1.3-to-8.2.2.1]]
- [[Upgrade from 8.2.2.3 to 8.2.7.3|Upgrade-use-case-from-8.2.2.3-to-8.2.7.3]]

### Important versions

- `8.1.13.1` - Optional, when you have a lot of customized code and 8.2.2.1 is failing in most places.
- `8.2.2.1` - This is a very important step everyone should have. After this version, `drush entup` stops working. In this version, we finally migrated to the core media subsystem, and before going further it is important to upgrade media by upgrading your site to this version first.
- `8.2.7.3` - This is a very stable Drupal 8 based Open Y with a bunch of contrib module updates. This is one of the last Drupal 8 based Open Y versions before the upgrade to Drupal 9 core. Also, in 8.2.7.0 and 8.2.7.1 we started to introduce multiple version constraints in `composer.json` to allow developers to choose between the minimum or latest dependency versions. This is for securing the upgrade path as well as adding flexibility for version selection if needed.
- `9.2.8.0` - Drupal 9 version which must be used in the upgrade path before going to 9.2.8.1+. This version added 9.0-9.1 Drupal Core and disabled deprecated components.
- `9.2.10.0` - Removed a bunch of unused modules from distribution.

See [[Version Constraints practices for Open Y|Composer-version-constraints-for-Open-Y]]

## Known issues

If you are faced with an issue when `composer` installs an improper version of `drupal/core` for the chosen version of Open Y from the list above, please use this trick in order to downgrade:

```sh
composer require drupal/core-recommended:9.2.8
```

Run the above command where your `docroot` is. Use the current core version instead of `9.2.8`.

