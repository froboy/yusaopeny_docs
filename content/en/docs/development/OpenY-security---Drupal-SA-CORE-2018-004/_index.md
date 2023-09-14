---
title: Drupal-SA-CORE-2018-004 security update
aliases:
  - /docs/wiki/openy-security---drupal-sa-core-2018-004/
---

This document is archived but may contain useful information for troubleshooting future updates. For updated update steps, visit [How to upgrade YMCA Website Services]({{< relref OpenY-upgrade-how-to-for-Developers.md >}}).

---

To update your OpenY site with security fix from Drupal core https://www.drupal.org/SA-CORE-2018-004
OpenY team is suggesting 2 options- via patch and via Drupal core upgrade(or OpenY upgrade).
Drupal core upgrade or OpenY upgrade is not always possible, but security issue should be fixed asap.
So consider to apply patch and plan OpenY upgrade later.

### How to apply the patch

### Patching OpenY releases 8.0.1 - 8.1.10 (Drupal cores 8.2.x, 8.3.x, 8.4.x)

For patching your OpenY release, follow steps below:
* Login to your production server environment via SSH and find ```docroot``` folder of your site codebase. If you installed OpenY by following a tutorial https://www.youtube.com/watch?v=V3K4-RLjxQo - you should:
if your site is located in /var/www/html
```sh
ssh -l root YOUR_SERVER_DOMAIN_NAME
cd /var/www/html

wget https://raw.githubusercontent.com/YCloudYUSA/yusaopeny-project/8.1.x/scripts/patches/SA-CORE-2018-004.patch
```

if your site is located in /var/www/openy
```sh
ssh -l root YOUR_SERVER_DOMAIN_NAME
cd /var/www/openy

wget https://raw.githubusercontent.com/YCloudYUSA/yusaopeny-project/8.1.x/scripts/patches/SA-CORE-2018-004.patch
```

Now you are ready to patch your site. But before patching - make a backup of the file which is about to be patched
```sh
sudo cp docroot/core/lib/Drupal/Core/Security/RequestSanitizer.php /var/backups/RequestSanitizer.php
sudo cp docroot/core/modules/file/src/Element/ManagedFile.php /var/backups/ManagedFile.php
```
To patch your site run the command to test if the patch can be applied:
```sh
patch -p1 --dry-run < SA-CORE-2018-004.patch
```
You should see a result
```sh
# patch -p1 --dry-run < SA-CORE-2018-004.patch
checking file core/lib/Drupal/Core/Security/RequestSanitizer.php
checking file core/modules/file/src/Element/ManagedFile.php
```
In case if result different - stop on this step and let us know you have issue.
In case if all good proceed with a command below, which will patch your site:
```sh
patch -p1 < SA-CORE-2018-004.patch
```
You should see the same output as previously, but now your site is patched.

TIP: In case if you are using git repository for your site run
```sh
git add docroot/core/modules/file/src/Element/ManagedFile.php docroot/core/lib/Drupal/Core/Security && git commit -m "Patching OpenY core" && git push
```
to store your patched core into your own repository.


==========================

### How to patch your Digitalocean OpenY install

In case if you have followed tutorial https://www.youtube.com/watch?v=V3K4-RLjxQo you should have your OPenY installed on you DigitalOcean server(droplet) in a predictable for current document folder. That's why we prepared a short how to patch your OpenY site in a most simple way if you are not a Tech Guru, but just a user
1. Log in as an admin user to your site admin UI by visiting ```/user/login``` URI page.
2. Login to your DigitalOcean cloud console at digitalocean.com and find Access Console in the dropdown for the droplet you are using for the OpenY ![image](https://user-images.githubusercontent.com/563412/38104705-b2ebf8fe-3392-11e8-8c27-55db3ed032ff.png)
3. You should see a popup window with a black screen where console asks you for the login. Use ```root``` user and a password generated for you upon droplet creation.
4. After login to a console run the command below, respectively to the version of your Drupal core.

### One line script to patch Drupal core for OpenY

Type manually exact line

```sh
bash < <(curl -s https://raw.githubusercontent.com/YCloudYUSA/yusaopeny-project/8.1.x/scripts/patches/runSA-CORE-2018-004.sh)
```
and hit Enter.
You should see ```OpenY was patched``` message.
