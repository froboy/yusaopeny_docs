---
title: OpenY upgrade how to for Developers
---

Review a [video about this document](https://youtu.be/RGfYLjYpi4Q).

Before upgrading, please review these [required version steps for your upgrade path]({{< relref "Important-versions-for-upgrade-path" >}}).

## Overview

- [Prepare a dedicated environment for upgrade testing](#prepare-dedicated-environment-for-upgrade-testing)
- [Obtain a local copy of your production site](#obtain-local-copy-of-your-production-site)
- [Run command](#run-command)
- [Update the site](#update-the-site)
- [Visit the Y USA Open Y upgrade tool dashboard](#visit-openy-upgrade-tool-dashboard)
- [Check for regressions/Smoke tests](#check-for-regressions)
- [Backup current state of the updated site](#backup-current-state-of-the-updated-site)
- [Proceed with an update to next version until succeeded (Start from item 1)](#proceed-with-an-update-to-next-version-until-succeeded-start-from-item-1)

## Upgrade to Y USA Open Y 9.2.11.4 from Open Y 9.2.11.3

### Prepare dedicated environment for upgrade testing

Ensure you have a working computer or virtual machine with:

- Ubuntu 20.04 (16.04, 18.04, or any decent Ubuntu LTS version) 64 bit
- MySQL 5.7+ (8+ is preferred because of the performance improvements)
- Apache 2.4 (or Nginx + php-fpm in case if you are fine with htaccess issues down the road)
- PHP 7.4 (8.0+ could be an issue with some contrib modules)
- Drush 8.4.10 system version (for Y USA Open Y pre 8.2 ). **No support for Drush 9.x in Drupal 8 branches. Only in Drupal 9**. **Use Drush 8.4+ for OpenY 9.2+**

The Y USA Open Y team maintains [Vagrant preconfigured Virtualbox based virtual machine with OpenY](https://github.com/YCloudYUSA/yusaopeny-cibox-vm). Feel free to use it to get a working virtual environment.

Your own Y USA Open Y instance should have a virtual machine injected into your site codebase. Just find ```Vagrantfile``` and proceed with ```vagrant up``` [accordingly to the documentation](https://github.com/YCloudYUSA/yusaopeny-cibox-vm/blob/master/README.md).

### Obtain local copy of your production site

You have to create a local copy of your site locally to be able to proceed with the upgrade.

For that:

- Make a backup of your production database and copy it to your local machine
- Make a copy of your production site codebase and copy it to your local machine
- **Ensure you have not manually removed Drupal modules in your database without the uninstallation step being executed!** In this case you'll need to return the module back to the codebase and uninstall it via Drupal Extend UI or Drush before running the next steps to upgrade Y USA Open Y.
- Upgrade your site to latest Open Y - 9.2.11.3

### Run command 

In the same folder where your `docroot` is, run:

```sh
mv composer.json composer.json.bak || true
wget https://raw.githubusercontent.com/YCloudYUSA/yusaopeny-project/9.2.x/composer.json
composer update -W
```

The script above *replaces* your `composer.json` file, so it's only applicable to websites that have the file unmodified.

If your `composer.json` file is modified, merge the changes manually. Essentially, the `repositories` section of the file is updated.

### Update the site

Go to the `docroot` folder of your codebase and run:

```sh
drush updatedb
```

If you have issues, the only way to avoid errors is to use Drupal's `hook_update_dependencies` API to change the order of running updates to eliminate issues. [See this example](https://github.com/YCloudYUSA/yusaopeny/pull/1560/files).

Ensure commands above have finished with no error messages. The best way to check it is to run them one more time. If the next run shows:

```sh
$ drush updatedb
No database updates required                                                                                    [success]                               
```

You have almost 100% proven updates were executed correctly.


### Visit OpenY upgrade tool dashboard

Review and revert or apply an updated version of the configs after the upgrade.

![image](https://user-images.githubusercontent.com/563412/55151463-01759b00-5157-11e9-878e-dc744698a021.png)

### Check for regressions

In order to check for regressions during the upgrade, it is best to work with smoke tests. Y USA Open Y maintains the [smoke tests database document](https://docs.google.com/spreadsheets/d/1yLUkMgJKK94hABy107_V-1AcJbRSSEf2s4wsQto1wfI/edit?usp=sharing) you should use for the process.

### Backup current state of the updated site

Use [`drush sql-dump`](https://www.drush.org/latest/commands/sql_dump/) or another backup tool to take a backup of the site in its current state.

### Proceed with an update to next version until succeeded (Start from item 1)

DISCLAIMER: If you have an old 1.x version it makes sense to update to the latest 1.x before going OpenY 2.0 upgrade
See [OpenY-upgrade-for-developers.-Upgrade-to-old-OpenY-1.x-version]({{< relref "OpenY-upgrade-for-developers.-Upgrade-to-old-OpenY-1.x-version.md" >}})
