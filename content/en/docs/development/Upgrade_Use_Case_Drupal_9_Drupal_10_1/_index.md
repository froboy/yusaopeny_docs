---
title: "Upgrading from 9.2.11.5 to 10.3"
---

## Scenario

A YMCA website is currently running on Y USA Open Y (`openy-9.x-2.11.5`) using Drupal 9. They want to upgrade to the latest YMCA Website Services distribution (`10.3`) on Drupal 10.

## Upgrade Steps

1. **Prepare for Upgrade to WS**

   * Ensure your site is on the latest Y USA Open Y 9.x release

      ```bash
      composer require -W ycloudyusa/yusaopeny:9.2.13.0 drupal/core-project-message:^9.5  drupal/core-composer-scaffold:^9.5 drupal/core-recommended:^9.5
      ```

   * Run database updates

      ```bash
      ../vendor/drush/drush/drush updatedb -l $SITE_URL
      ```

2. **Upgrade to WS 10.2**

   * Require the 10.2.14 release of Y USA Open Y and update Drupal core and dependencies

      ```bash
      composer require -W ycloudyusa/yusaopeny:10.2.14 drupal/core-project-message:^10.0.11  drupal/core-composer-scaffold:^10.0.11 drupal/core-recommended:^10.0.11 drupal/core:^10.0.11 'drupal/smtp:^1.4' consolidation/robo:^4
      ```

3. **Address QuickEdit/RDF Dependency Issue**

   * Temporarily require QuickEdit and RDF

      ```bash
      composer require drupal/quickedit drupal/rdf
      ```

   * Run database updates

      ```bash
      ../vendor/drush/drush/drush updatedb -l
      ```

   * Remove and re-add QuickEdit to resolve dependency conflicts

      ```bash
      composer remove drupal/quickedit
      composer require drupal/quickedit drupal/rdf
      ```

4. **Upgrade to WS 10.3.0.1**

   * Require the 10.3.0.1 release

      ```bash
      composer require -W ycloudyusa/yusaopeny:10.3.0.1 drupal/core-project-message:^10.0.11  drupal/core-composer-scaffold:^10.0.11 drupal/core-recommended:^10.0.11 drupal/core:^10.0.11
      ```

   * Run database updates

      ```bash
      ../vendor/drush/drush/drush updatedb -l $SITE_URL
      ```

5. **Upgrade to WS 10.3.1**

   * Require the 10.3.1 release

      ```bash
      composer require -W ycloudyusa/yusaopeny:10.3.1 drupal/core-project-message:^10.0.11  drupal/core-composer-scaffold:^10.0.11 drupal/core-recommended:^10.0.11 drupal/core:^10.0.11
      ```

6. **Add CKEditor5 Paste Filter**

   * Require the CKEditor5 Paste Filter module

      ```bash
      composer require drupal/ckeditor5_paste_filter
      ```

   * Run database updates

      ```bash
      ../vendor/drush/drush/drush updatedb -l $SITE_URL
      ```

7. **Upgrade to WS 10.3.2**

   * Require the 10.3.2 release

      ```bash
      composer require -W ycloudyusa/yusaopeny:10.3.2 drupal/core-project-message:^10.0.11  drupal/core-composer-scaffold:^10.0.11 drupal/core-recommended:^10.0.11 drupal/core:^10.0.11
      ```

8. **Upgrade to WS 10.3.3.2**

   * Require the 10.3.3.2 release

      ```bash
      composer require -W ycloudyusa/yusaopeny:10.3.3.2
      ```

   * Run database updates

      ```bash
      ../vendor/drush/drush/drush updatedb -l $SITE_URL
      ```

9. **Address CKEditor5 Font Issue**

   * Uninstall the existing CKEditor5 Font module

      ```bash
      uninstall ckeditor5_font
      ```

   * Require the latest beta version of CKEditor5 Font

      ```bash
      composer require 'drupal/ckeditor5_font:^1.1@beta'
      ```

   * Enable the CKEditor5 Font module

      ```bash
      ../vendor/drush/drush/drush en ckeditor5_font
      ```

## Important Considerations

* **Backup:** Always back up your site and database before performing any major upgrades.
* **Testing:** Thoroughly test your site after each upgrade step on a staging environment before deploying to production.
* **Customizations:** If you have made significant customizations to your site, consult with a Drupal developer to ensure a smooth upgrade process.
* **Drush Path:** Adjust the `../vendor/drush/drush/drush` path if your Drush installation is located elsewhere.
* **$SITE_URL:** Replace `$SITE_URL` with the actual URL of your site.

**Disclaimer:** This use case provides a general outline for upgrading the YMCA Website Services Drupal distribution. Specific steps and commands may vary depending on your site's configuration and any additional modules or customizations you have installed. Always refer to the official YMCA Website Services documentation and Drupal.org for the most up-to-date information and best practices.
