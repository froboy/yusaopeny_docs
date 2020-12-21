Open Y has a pretty intense development timeline and in this document, we are marking important versions that should not be skipped while users upgrade their sites.

Example. If you are on Open Y 8.1.2 and want to upgrade to Open Y 8.2.8.5 you should make it in couple of steps
1. Upgrade 8.1.2 to 8.1.13.1
1. Upgrade 8.1.13.1 to 8.2.2.1
1. Upgrade 8.2.2.1 to 8.2.7.1
1. Upgrade 8.2.7.1 ...



* 8.1.13.1 ( optional, when you have a lot of customized code and 8.2.2.1 is failing in most places). 
* 8.2.2.1 ( this is a very important step everyone should have. After this version, `drush entup` stops working. In this version, we finally migrated to the core media subsystem, and before going further - important to upgrade media by upgrading your site to this version first.
* 8.2.7.1 ( this is a very stable Drupal 8 based Open Y with a bunch of contrib modules updates ). This is one of the last Drupal 8 based Open Y versions before upgrade to Drupal 9 core. Also, in 8.2.7.0(8.2.7.1) we started to introduce multiple version constraints in composer.json to allow developers to choose between the minimum and latest dependency versions. This should secure the upgrade path.

