# Welcome to Open Y wiki

## Requirements

* php-cli 7.4
* composer 2

## Steps

1. Obtain latest development code of Open Y

```sh
composer create-project ymcatwincities/openy-project:9.2.x-development-dev openy7.4
```

2. Add phpcompatibility to require-dev section

```
cd open7.4
composer require --dev phpcompatibility/php-compatibility
./vendor/bin/phpcs -p . --standard=PHPCompatibility --runtime-set testVersion 7.4 --config-set installed_paths vendor/phpcompatibility/php-compatibility
```

3. Generate report

```
./vendor/bin/phpcs -p . --standard=PHPCompatibility --runtime-set testVersion 7.4 --report-file=report.txt
```





