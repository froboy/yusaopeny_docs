---
title: OpenY upgrade how to for Developers
---

Review a [video about this document](https://youtu.be/RGfYLjYpi4Q).

Before upgrading, please review these [required version steps for your upgrade path]({{< relref "Important-versions-for-upgrade-path" >}}).

## Overview

- [Prepare a dedicated environment for upgrade testing](#prepare-dedicated-environment-for-upgrade-testing)
- [Obtain a local copy of your production site](#obtain-local-copy-of-your-production-site)
- [Run command with next newer version (replace NEW_VERSION_HERE with the version you are upgrading to, e.g 8.2.0.7 )](#run-command-with-next-never-version-replace-new_version_here-with-the-version-you-are-upgrading-to-eg-8207)
- [Enable Open Y introduced modules in case if you are updating from very old version or if they are disabled intentionally](#enable-openy-introduced-modules-in-case-if-you-are-updating-from-very-old-version-or-if-they-are-disabled-intentionally)
- [Verify if the Media Entity to Media in Core migration is possible](#verify-if-the-media-entity-to-media-in-core-migration-is-possible)
- [Update the site](#update-the-site)
- [Visit the Open Y upgrade tool dashboard](#visit-openy-upgrade-tool-dashboard)
- [Check for regressions/Smoke tests](#check-for-regressions)
- [Backup current state of the updated site](#backup-current-state-of-the-updated-site)
- [Proceed with an update to next version until succeeded (Start from item 1)](#proceed-with-an-update-to-next-version-until-succeeded-start-from-item-1)

## Upgrade to Open Y 2.x

### Prepare dedicated environment for upgrade testing

Ensure you have a working computer or virtual machine with:

- Ubuntu 20.04 (16.04, 18.04, or any decent Ubuntu LTS version) 64 bit
- MySQL 5.5+ (5.7 is preferred because of the performance improvements)
- Apache 2.4 (or Nginx + php-fpm in case if you are fine with htaccess issues down the road)
- PHP 7.4 (8.0+ could be an issue with some contrib modules)
- Drush 8.4.10 system version (for Open Y pre 8.2 ). **No support for Drush 9.x in Drupal 8 branches. Only in Drupal 9**. **Use Drush 8.4+ for OpenY 9.2+**

The Open Y team maintains [Vagrant preconfigured Virtualbox based virtual machine with OpenY](https://github.com/ymcatwincities/openy-cibox-vm). Feel free to use it to get a working virtual environment.

Your own Open Y instance should have a virtual machine injected into your site codebase. Just find ```Vagrantfile``` and proceed with ```vagrant up``` [accordingly to the documentation](https://github.com/ymcatwincities/openy-cibox-vm/blob/master/README.md).

### Obtain local copy of your production site

You have to create a local copy of your site locally to be able to proceed with the upgrade.

For that:

- Make a backup of your production database and copy it to your local machine
- Make a copy of your production site codebase and copy it to your local machine
- **Ensure you have not manually removed Drupal modules in your database without the uninstallation step being executed!** In this case you'll need to return the module back to the codebase and uninstall it via Drupal Extend UI or Drush before running the next steps to upgrade Open Y.

### Run command with next never version ( replace NEW_VERSION_HERE with the version you are upgrading to, e.g 8.2.0.7 )

In the same folder where your `docroot` is, run:

```sh
mv composer.json composer.json.bak || true
wget https://raw.githubusercontent.com/ymcatwincities/openy-project/8.2.x/composer.json
cd docroot/profiles/contrib/openy/
rm -f yparse*
wget https://raw.githubusercontent.com/ymcatwincities/openy-project/8.2.x/scripts/yparse.sh
drush cr
sh yparse.sh | xargs drush en -y
cd ../../../../
composer require ymcatwincities/openy:NEW_VERSION_HERE --no-update
composer update --prefer-dist --with-dependencies --prefer-stable --no-suggest
```

The script above *replaces* your `composer.json` file, so it's only applicable to websites that have the file unmodified.

If your `composer.json` file is modified, merge the changes manually. Essentially, the `repositories` section of the file is updated.

### Enable OpenY introduced modules in case if you are updating from very old version or if they are disabled intentionally.

```sh
cd docroot
drush en openy_upgrade_tool openy_er openy_prgf_loc_finder openy_map openy_data_wrapper openy_loc_branch openy_focal_point media_directories_ui
```

Sometimes it is important to get the latest [openy_upgrade_tool](https://github.com/ymcatwincities/openy/tree/8.x-2.x/modules/custom/openy_upgrade_tool) from the repository even if you are not updating to the latest version of Open Y. You'll be able to disable them in the end once all updates are executed successfully.

### Verify if the Media Entity to Media in Core migration is possible ( only for upgrades from OpenY 1.x to 2.x )

Go to the `docroot` directory of your codebase and execute:

```sh
drush mecu
```

If the output looks like the following lines, you are good to proceed with database updates.

```
✓ SUCCESS: All upgrade requirements are met and                      [ok]
you can proceed with the DB updates.
Drupal core is the correct version (>= 8.6.0). [8.6.10 detected]     [ok]
The contributed "Media" module is not installed.                     [ok]
All provider plugins and modules depending on media_entity are       [ok]
up-to-date.
Site uses EXIF handling and the "Media Entity Image EXIF" module is  [ok]
available.
```

Follow the instructions of the output messages if they contain warnings or errors. Take a look at the [detailed guide](https://www.drupal.org/node/2863992) if you have any troubles.

### Update the site

Go to the `docroot` folder of your codebase and run:

```sh
drush updatedb
drush entup
```

We found, in some instances, because of the complexity of the database you'd need to run this command above up to 6 times to get all entities and updates run to the end. You may ignore errors of the commands until there are no errors after the final run. So:

```
drush updatedb
drush entup
drush updatedb
drush entup
drush updatedb
drush entup
drush updatedb
drush entup
drush updatedb
drush entup
```

Please any log errors as issues for the QA team investigate.

If you have issues, the only way to avoid errors is to use Drupal's `hook_update_dependencies` API to change the order of running updates to eliminate issues. [See this example](https://github.com/ymcatwincities/openy/pull/1560/files).

Ensure commands above have finished with no error messages. The best way to check it is to run them one more time. If the next run shows:

```sh
$ drush updatedb
No database updates required                                                                                    [success]
$ drush entup
No entity schema updates required                                                                               [success]
```

You have almost 100% proven updates were executed correctly.

Sometimes, you could face an error like:

> openy.terms_and_conditions.schema depends on the Open Y module that will not be installed after import.

In this case, please, ensure that the module connected with this config is enabled.

To make it happen, please execute this command:

`drush ev "Drupal::service('module_installer')->install(['module_with_problem']);"`

### Visit OpenY upgrade tool dashboard

Review and revert or apply an updated version of the configs after the upgrade.

![image](https://user-images.githubusercontent.com/563412/55151463-01759b00-5157-11e9-878e-dc744698a021.png)

### Check for regressions

In order to check for regressions during the upgrade, it is best to work with smoke tests. Open Y maintains the [smoke tests database document](https://docs.google.com/spreadsheets/d/1yLUkMgJKK94hABy107_V-1AcJbRSSEf2s4wsQto1wfI/edit?usp=sharing) you should use for the process.

### Backup current state of the updated site

Use [`drush sql-dump`](https://www.drush.org/latest/commands/sql_dump/) or another backup tool to take a backup of the site in its current state.

### Proceed with an update to next version until succeeded (Start from item 1)

DISCLAIMER: If you have an old 1.x version it makes sense to update to the latest 1.x before going OpenY 2.0 upgrade
See [OpenY-upgrade-for-developers.-Upgrade-to-old-OpenY-1.x-version]({{< relref "OpenY-upgrade-for-developers.-Upgrade-to-old-OpenY-1.x-version.md" >}})
