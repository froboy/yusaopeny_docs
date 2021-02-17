Check video about this document: https://youtu.be/RGfYLjYpi4Q

DISCLAIMER: If you have old 1.x version it makes sense to update to latest 1.x before going OpenY 2.0 upgrade. [Check here](https://github.com/ymcatwincities/openy/wiki/OpenY-upgrade-for-developers.-Upgrade-to-old-OpenY-1.x-version)


[Key OpenY versions worth using as intermediate steps for upgrading from very old OpenY versions](https://github.com/ymcatwincities/openy/wiki/Important-versions-for-upgrade-path)
 

[Upgrade use case - from 8.1.3 to 8.2.2.1](https://github.com/ymcatwincities/openy/wiki/Upgrade-OpenY-8.1.3-to-8.2.2.1)

**Table of Contents**

- [Prepare dedicated environment for upgrade testing](#prepare-dedicated-environment-for-upgrade-testing)
- [Obtain local copy of your production site](#obtain-local-copy-of-your-production-site)
- [Run command with next never version ( replace NEW_VERSION_HERE with the version you are upgrading to, e.g 8.2.0.7 )](#run-command-with-next-never-version-replace-new_version_here-with-the-version-you-are-upgrading-to-eg-8207)
- [Enable OpenY introduced modules in case if you are updating from very old version or if they are disabled intentionally.](#enable-openy-introduced-modules-in-case-if-you-are-updating-from-very-old-version-or-if-they-are-disabled-intentionally)
- [Verify if the Media Entity to Media in Core migration is possible](#verify-if-the-media-entity-to-media-in-core-migration-is-possible)
- [Update the site](#update-the-site)
- [Visit OpenY upgrade tool dashboard](#visit-openy-upgrade-tool-dashboard)
- [Check for regressions/Smoke tests](#check-for-regressions)
- [Backup current state of the updated site](#backup-current-state-of-the-updated-site)
- [Proceed with an update to next version until succeeded (Start from item 1)](#proceed-with-an-update-to-next-version-until-succeeded-start-from-item-1)


Hi, dear OpenY community

This document aims to cover the need of upgrade OpenY from older versions to recent ones. 

Upgrade to Open Y 2.x version
=====

### Prepare dedicated environment for upgrade testing

Ensure you have working computer or virtual machine with 
 - Ubuntu 14.04(16.04, 18.04 or any decent Ubuntu LTS versions) 64 bit
 - MySQL 5.5+(5.7 preffered because of the performance improvements)
 - Apache 2.4(or Nginx + php-fpm in case if you are fine with htaccess issues down the road)
 - PHP 7.2 (7.3+ could be an issue with some contrib modules)
 - Drush 8.1.17 version ( OpenY pre 8.2 ). **No support for Drush 9.x yet**. **Use drush 8.3+ for OpenY 8.2+**

OpenY team maintains [Vagrant preconfigured Virtualbox based virtual machine with OpenY](https://github.com/ymcatwincities/openy-cibox-vm). Feel free to use it to get working virtual environment.
Your own OpenY instance should have Virtual machine injected into your site codebase. Just find ```Vagrantfile``` and proceed with ```vagrant up``` [accordingly to the documentation](https://github.com/ymcatwincities/openy-cibox-vm/blob/master/README.md).

### Obtain local copy of your production site

You have to create local copy of your site locally to be able to proceed with the upgrade.
For that
 - Make a backup of your production database and copy it to your local machine
 - Make a copy of your production site codebase and copy it to your local machine
 - **Ensure you have no manually removed Drupal modules in your database without uninstallation step being executed!** In this case you'll need to return module back and uninstall it via Drupal Extend UI or Drush before running next steps to upgrade OpenY

### Run command with next never version ( replace NEW_VERSION_HERE with the version you are upgrading to, e.g 8.2.0.7 )

In a same folder where is your ```docroot``` folder run

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
The script above *replaces* your `composer.json` file, so it's only applicable to the websites that have the file unmodified.

If your `composer.json` file is modified, merge the changes manually. Essentially, the `repositories` section of the file is updated.


### Enable OpenY introduced modules in case if you are updating from very old version or if they are disabled intentionally.

```sh
cd docroot
drush en openy_upgrade_tool openy_er openy_prgf_loc_finder openy_map openy_data_wrapper openy_loc_branch 
```
Sometimes it is important to get latest [openy_upgrade_tool](https://github.com/ymcatwincities/openy/tree/8.x-2.x/modules/custom/openy_upgrade_tool) from repository even if you are updating to not latest version of OpenY.
You'll be able to disable them in the end once all updates executed successfully

### Verify if the Media Entity to Media in Core migration is possible ( only for upgrades from OpenY 1.x to 2.x )

Go to `docroot` directory of your codebase and execute:
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

Follow the instructions of the output messages if they contain warnings or errors.
Take a look at the [detailed guide](https://www.drupal.org/node/2863992) if you have and troubles.

### Update the site

Go to docroot folder of your codebase and run
```sh
drush updatedb
drush entup
```
We found on some of the instances, because of the complexity of the database you'd need to run command above up to 6 times to get all entities and updates run to the end. You may ignore errors of the commands above until there won't be any after final run
So
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
above is the example of the process we had to follow on some instances.
Ensure to log errors for the QA team to text respective subsystems afterwards
In case if you have issues - the only way to avoid errors is to use Drupal's hook_update_dependencies API to change order of running updates to eliminate issues. Example is here https://github.com/ymcatwincities/openy/pull/1560/files

Ensure commands above finished with no error messages. Best way to check it - run them one more time. If next run shows 
```sh
$ drush updatedb
No database updates required                                                                                    [success]
$ drush entup
No entity schema updates required                                                                               [success]
```
You almost 100% proved updated were executed correctly.

Sometimes, you could face with error like: 
> openy.terms_and_conditions.schema depends on the Open Y module that will not be installed after import.

In this case, please, ensure that module, connected with this config is enabled.
To make it happen, please execute this command: 

`drush ev "Drupal::service('module_installer')->install(['module_with_problem']);"`

### Visit OpenY upgrade tool dashboard 
Review and revert or apply updated version of the configs after upgrade. 
![image](https://user-images.githubusercontent.com/563412/55151463-01759b00-5157-11e9-878e-dc744698a021.png)

### Check for regressions

In order to check for regressions during upgrade, it is best to work with smoke tests. Open Y maintains the [smoke tests database document](https://docs.google.com/spreadsheets/d/1yLUkMgJKK94hABy107_V-1AcJbRSSEf2s4wsQto1wfI/edit?usp=sharing) you should use for the process.

### Backup current state of the updated site

...

### Proceed with an update to next version until succeeded (Start from item 1)

DISCLAIMER: If you have old 1.x version it makes sense to update to latest 1.x before going OpenY 2.0 upgrade
See https://github.com/ymcatwincities/openy/wiki/OpenY-upgrade-for-developers.-Upgrade-to-old-OpenY-1.x-version

