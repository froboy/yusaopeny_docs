To update your OpenY site with security fix from Drupal core https://www.drupal.org/sa-core-2018-002
OpenY team is suggesting 2 options- via patch and via Drupal core upgrade(or OpenY upgrade).
Drupal core upgrade or OpenY upgrade is not always possible, but security issue should be fixed asap.
So consider to apply patch and plan OpenY upgrade later.

### How to apply patch

### Patching OpenY releases 8.0.1 - 8.1.0 (Drupal core 8.2.x)

For patching your very old OpenY release it is highly recommended to upgrade OpenY to latest version or at least to one of the 8.1.1-8.1.6 (Drupal core 8.3.x) with Drupal core upgrade to 8.3.9 https://www.drupal.org/project/drupal/releases/8.3.9 . In case if it is not possible right now, follow steps below:
* Login to your production server environment via SSH and find ```docroot``` folder of your site codebase. If you installed OpenY by following a tutorial https://www.youtube.com/watch?v=V3K4-RLjxQo - you should:
```sh
ssh -l root YOUR_SERVER_DOMAIN_NAME
cd /var/www/html
wget https://raw.githubusercontent.com/ymcatwincities/openy-project/8.1.x/scripts/patches/8.2.x.patch
```
Now you are ready to patch your site. But before patching - make a backup of the file which is about to be patched
```sh
cp docroot/core/lib/Drupal/Core/DrupalKernel.php /var/backups/DrupalKernel.php
```
To patch your site run the command to test if the patch can be applied:
```sh
patch -p1 --dry-run < 8.2.x.patch
```
You should see a result
```sh
# patch -p1 --dry-run < 8.2.x.patch 
checking file docroot/core/lib/Drupal/Core/DrupalKernel.php
checking file docroot/core/lib/Drupal/Core/Security/RequestSanitizer.php
```
In case if result different - stop on this step and let us know you have issue.
In case if all good proceed with a command below, which will patch your site:
```sh
patch -p1 < 8.2.x.patch
```
You should see the same output as previously, but now your site is patched.

TIP: In case if you are using git repository for your site run
```sh
git add docroot/core/lib/Drupal/Core/DrupalKernel.php docroot/core/lib/Drupal/Core/Security && git commit -m "Patching OpenY core" && git push
```
to store your patched core into your own repository. 

=================================

### OpenY version prior to 8.1.0 including 8.1.0

Drupal core version is 8.2.x there, so you have to upgrade to at least 8.1.1 OpenY(optional) and additionally upgrade core to suggested latest 8.3.x version 

### OpenY versions 8.1.1-8.1.6

Upgrade Drupal core to latest 8.3.9 version

```sh
composer require drupal/core:8.3.9 --no-update
composer update --prefer-dist --with-dependencies --prefer-stable --prefer-lowest --no-suggest
```

### OpenY versions 8.1.7-8.1.9

Upgrade Drupal core to latest 8.4.6 version

```sh
composer require drupal/core:8.4.6 --no-update
composer update --prefer-dist --with-dependencies --prefer-stable --prefer-lowest --no-suggest
```

### All commands below should be run in non-production environment!!!

### How to upgrade Drupal core without updating OpenY

Usually your OpenY site codebase looks like
![image](https://user-images.githubusercontent.com/563412/38021333-33d15be4-3285-11e8-9798-e8605e2422a8.png)

For running console commands below you should go to the directory where composer.json is located.

To get your Drupal core code updated follow the steps below:

```sh
composer require drupal/core:NEW_VERSION_HERE --no-update
composer update --prefer-dist --with-dependencies --prefer-stable --prefer-lowest --no-suggest
```


To get your database updated to latest Drupal core follow the steps below:

```sh
cd docroot
drush updatedb -y
drush entup -y
```

### Update production environment

In case if above steps succeeded you need to deploy yuor codebase and database to production.
1. Backup production site (database, assets, codebase)
2. Copy new codebase over old (remove old one prior copying)
3. Import upgraded database over old one (drop and import)
4. Clear site cache