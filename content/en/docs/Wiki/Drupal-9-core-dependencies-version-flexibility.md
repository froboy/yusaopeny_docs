# Welcome to Open Y wiki

February 2021 release tagged Drupal core both 9.0.x and 9.1.x as allowed to be used.
Composer by default is installing the latest stable version, so a command 
```bash
composer create-project ymcatwincities/openy-project:dev-9.2.x-development OPENY --no-interaction
```

will install Open Y on latest 9.1.x Drupal core.
If there is a need to stay on Drupal 9.0.x stable core please use
```bash
composer create-project ymcatwincities/openy-project:dev-9.2.x-development OPENY --no-interaction
cd OPENY
composer require drupal/core:~9.0.7
```
where 9.0.7 - is a needed version for your Open Y instance

For modules see https://github.com/ymcatwincities/openy/wiki/Composer-version-constraints-for-Open-Y