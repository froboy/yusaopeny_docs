### Document work in progress

This is a recipe for upgrading very old OpenY to decent version.
Given the fact [Drupal 8.7+ has no support for automatic entity updates](https://www.drupal.org/node/3034742) ( BaseFieldDefinitions ) we have to upgrade to 8.2.2.1 of OpenY which is still on 8.6 Drupal Core

# Step by step update

* Use PHP7.1 for upgrade and install `php7.1-mysql php7.1-mcrypt php7.1-cli php7.1-common php7.1-curl php7.1-dev php7.1-fpm php7.1-gd php7.1-mysql php7.1-memcached php7.1-imagic php7.1-xml php7.1-xdebug php7.1-mbstring php7.1-soap php7.1-zip php7.1-xml`
* Go to the folder of OpenY code tree where `docroot` folder
* `mv composer.json composer.json.orig`
* `wget https://raw.githubusercontent.com/ymcatwincities/openy-project/8.2.x/composer.json`
* `composer require ymcatwincities/openy:8.2.2.1 --no-suggest --no-update`
* `composer install --ignore-platform-reqs --no-suggest`
* `composer update --prefer-stable --no-suggest`
* `cd docroot`
* `drush dl -y plugin-8.x-2.5 contribute-8.x-1.0-beta7 scheduler-8.x-1.0 views_block_filter_block datalayer simple_menu_icons rabbit_hole metatag simple_sitemap-8.x-2.9 easy_breadcrumb-8.x-1.6`
* `drush en openy_upgrade_tool openy_er openy_prgf_loc_finder openy_map openy_data_wrapper openy_loc_branch content_moderation focal_point`
* `drush ev "Drupal::service('module_installer')->install(['openy']);"` <- This steps fixes some hidden bug when `openy` profile removed from `core.extension` configuration for unknown reason.
* Manual step: Edit all yml files in `profiles` folder to comment `media.type.image` , `field.field.node.program.field_header_content`, `field.field.node.branch.field_location_amenities` in dependencies sections.

![image](https://user-images.githubusercontent.com/563412/64005803-bc94cc80-cb19-11e9-8137-702d141c48e5.png)

![image](https://user-images.githubusercontent.com/563412/64005817-c1598080-cb19-11e9-8a04-9be0c7f3a15a.png)

![image](https://user-images.githubusercontent.com/563412/64005820-c61e3480-cb19-11e9-9853-dbad3c17d851.png)


* run `drush updatedb -y` <- this will fail for the first time ( Media not installed yet ), disregard
* run `drush updatedb -y` <- this should run properly.
* run `drush entup`


