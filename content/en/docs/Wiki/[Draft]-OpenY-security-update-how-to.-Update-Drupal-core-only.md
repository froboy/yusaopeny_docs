### OpenY version prior to 8.1.0 including 8.1.0

Drupal core version is 8.2.x there, so you have to upgrade to at least 8.1.1 OpenY(optional) and additionally upgrade core to suggested latest 8.3.x version 

### OpenY versions 8.1.1-8.1.6

Upgrade Drupal core to latest 8.3.x version

### OpenY versions 8.1.7-8.1.9

Upgrade Drupal core to latest 8.4.x version



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
