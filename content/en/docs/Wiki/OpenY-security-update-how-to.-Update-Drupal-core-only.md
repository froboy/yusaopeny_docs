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

### Patching OpenY releases 8.1.1 - 8.1.6 (Drupal core 8.3.x)

For patching your relatively old OpenY release it is highly recommended to upgrade OpenY to latest version or at least to one of the 8.1.7-8.1.10 (Drupal core 8.4.x) with Drupal core upgrade to 8.4.6 https://www.drupal.org/project/drupal/releases/8.4.6 . In case if it is not possible right now, follow steps below:
* Login to your production server environment via SSH and find ```docroot``` folder of your site codebase. If you installed OpenY by following a tutorial https://www.youtube.com/watch?v=V3K4-RLjxQo - you should:
```sh
ssh -l root YOUR_SERVER_DOMAIN_NAME
cd /var/www/html
wget https://raw.githubusercontent.com/ymcatwincities/openy-project/8.1.x/scripts/patches/8.3.x.patch
```
Now you are ready to patch your site. But before patching - make a backup of the file which is about to be patched
```sh
cp docroot/core/lib/Drupal/Core/DrupalKernel.php /var/backups/DrupalKernel.php
```
To patch your site run the command to test if the patch can be applied:
```sh
patch -p1 --dry-run < 8.3.x.patch
```
You should see a result
```sh
# patch -p1 --dry-run < 8.3.x.patch 
checking file docroot/core/lib/Drupal/Core/DrupalKernel.php
checking file docroot/core/lib/Drupal/Core/Security/RequestSanitizer.php
```
In case if result different - stop on this step and let us know you have issue.
In case if all good proceed with a command below, which will patch your site:
```sh
patch -p1 < 8.3.x.patch
```
You should see the same output as previously, but now your site is patched.

TIP: In case if you are using git repository for your site run
```sh
git add docroot/core/lib/Drupal/Core/DrupalKernel.php docroot/core/lib/Drupal/Core/Security && git commit -m "Patching OpenY core" && git push
```
to store your patched core into your own repository. 

### Patching OpenY releases 8.1.7 - 8.1.9 (Drupal core 8.4.x)

For patching your OpenY release it is highly recommended to upgrade OpenY to latest version (8.1.10 or never) or at least to one of the 8.1.10 (Drupal core 8.4.x) with Drupal core upgrade to 8.4.6 https://www.drupal.org/project/drupal/releases/8.4.6 . In case if it is not possible right now, follow steps below:
* Login to your production server environment via SSH and find ```docroot``` folder of your site codebase. If you installed OpenY by following a tutorial https://www.youtube.com/watch?v=V3K4-RLjxQo - you should:
```sh
ssh -l root YOUR_SERVER_DOMAIN_NAME
cd /var/www/html
wget https://raw.githubusercontent.com/ymcatwincities/openy-project/8.1.x/scripts/patches/8.4.x.patch
```
Now you are ready to patch your site. But before patching - make a backup of the file which is about to be patched
```sh
cp docroot/core/lib/Drupal/Core/DrupalKernel.php /var/backups/DrupalKernel.php
```
To patch your site run the command to test if the patch can be applied:
```sh
patch -p1 --dry-run < 8.4.x.patch
```
You should see a result
```sh
# patch -p1 --dry-run < 8.4.x.patch 
checking file docroot/core/lib/Drupal/Core/DrupalKernel.php
checking file docroot/core/lib/Drupal/Core/Security/RequestSanitizer.php
```
In case if result different - stop on this step and let us know you have issue.
In case if all good proceed with a command below, which will patch your site:
```sh
patch -p1 < 8.4.x.patch
```
You should see the same output as previously, but now your site is patched.

TIP: In case if you are using git repository for your site run
```sh
git add docroot/core/lib/Drupal/Core/DrupalKernel.php docroot/core/lib/Drupal/Core/Security && git commit -m "Patching OpenY core" && git push
```
to store your patched core into your own repository. 