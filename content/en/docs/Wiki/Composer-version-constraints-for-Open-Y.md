Welcome to the Open Y wiki

In 2020 due to changes in Drupal core release management and demand from Open Y customers to improve upgrade path flexibility and stability Open Y team added extended composer version constraints in order to provide information about stability and add flexibility in process of choosing dependencies versions.

Examples from [composer.json](https://github.com/ymcatwincities/openy/blob/9.x-2.x/composer.json)

* `"drupal/ckeditor_bootstrap_buttons": "^1.2 || ^2.0.0",` - this line means previous version was 1.2 or any 1.x starting from 1.2, and latest tested - 2.0.0 with allowed any stable 2.x starting from 2.0.0
* `"drupal/custom_formatters": "^3.0 || ^3.0@beta",` - tested with 3.0 beta of custom_formatters and allowed any 3.x starting from 3.0 (when it will be released)

By having multiple OR ( || ) conditions we are providing information for developers which versions could be used for the upgrade to. There are cases when the latest, even stable version of dependency could be incompatible with some other functionality and it makes sense to keep the version older while functionality is in the process of upgrading. 

For example, if, for some reason, custom_formatters 3.0 won't be compatible with any of Open Y dependencies at a time of release, developer can select an older beta version in order to proceed with the upgrade. 

For selecting a specific version of dependency when you do upgrade of Open Y - add dependency and it's version alongside with Open Y at a `composer require` step

Example

from [upgrade doc](https://github.com/ymcatwincities/openy/wiki/OpenY-upgrade-how-to-for-Developers)
```bash
composer require ymcatwincities/openy:NEW_VERSION_HERE --no-update
composer update --prefer-dist --with-dependencies --prefer-stable --no-suggest
```

change dependency version

```bash
composer require ymcatwincities/openy:NEW_VERSION_HERE --no-update
composer require drupal/custom_formatters:3.0@beta1
```

You can change any of the dependency versions without upgrading Open Y by running the only `composer require` command and Drupal Update DB routines afterward.

Check [official Composer documentation about version constraints](https://getcomposer.org/doc/articles/versions.md).



