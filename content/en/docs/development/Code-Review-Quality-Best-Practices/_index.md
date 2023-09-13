---
title: Code Review Quality Best Practices
aliases:
  - /docs/wiki/code-review-quality-best-practices/
---

This document serves as an addition to our [Code of Conduct and Best Practices]({{< relref "Open-Y-Code-of-Conduct-and-Best-Practices" >}}). It is more technical and in-depth for specific cases that were discussed during code quality review processes the YMCA Website Services team has in place. During this process, all code should be reviewed by 1-2 developers before being merged into the YMCA Website Services codebase.

# General Rules

Components in YMCA Website Services (whether modules, themes, or other code structures) should be, as much as possible, reusable and atomic. All features, content types, settings, styles, etc. should be bundled together to create a cohesive component.

1. General naming conventions
    1. Features module naming
        1. **openy\_${entity\_type|abbr}\_${entity_bundle|abbr}\_${feature|optional}**
            1. Example: **openy_node_blog_feature**
            1. **openy_prgf_sc_feature** -> OpenY Paragraph Simple Content (name within yml)
    1. Fields naming (<=20 chars)
        1. **field\_${entity\_type|abbr}\_${entity\_bundle|abbr}\_{name|abbr}**
            1. Example: **field_prgf_sc_body**
    1. **All descriptions are mandatory!**
1. Module naming conventions - Depending on the context we should choose the name from this list:
    1. **\${project_name|abbr}_\${business_name|abbr**} - when the code looks like legacy and has specifics that are not ready to be open-sourced
    1. **openy_${business_name|abbr}** - when the code is ready to be ejected to OpenY package
    1. **${business_name}** - when the code is so abstract that it has no connection to OpenY and is ready to be hosted on Drupal.org as an independent project.

## Code Sharing

To support reuse by the community, the MODULE-NAME should relate to the business logic of the module. It is not good to create modules by abstracting them out of the business. All modules that have been shared to drupal.org from past projects were possible to share only because they represent some feature, tied to a business need. For example:

- personify - module for SOAP related methods for working with Personify API
- acrypt - Asymmetric crypt algorithm

and so on.

# PHP

## Return early pattern

To keep readability in functions and methods, it is wise to return early if simple conditions apply that can be checked at the beginning of a method:

```php
<?php

function foo($bar, $baz)
{
    if ($foo) {
        // logic goes here
        return $calculated_value;
    } else {
        return null;
    }
}
?>
```

It's better to return early, keeping indentation and brainpower needed to follow the code low.

```php
<?php

function foo($bar, $baz)
{
    if (!$foo) {
        return null;
    }

    // logic goes here
    return $calculated_value;
}
?>
```

## Define early pattern

When you have a condition that aims to change the value of a variable without additional logic, get rid of ```if else elseif``` code and instead define your variable early and change it via conditions.

Before:

```php
if ($a = 'hello') {
 $text = 'Welcome to site';
}
else {
 $text = 'Register please';
}
```

After:

```php
$text = 'Register please';
if ($a = 'hello') {
 $text = 'Welcome to site';
}
```

## Null Checks with `isset`

[`isset()`](https://www.php.net/manual/en/function.isset.php) verifies if set and not null. There is no need to do additional verification against NULL.

Before:

```php
...
'video' => (isset($feed['profile_media_videos']) || $feed['profile_media_videos'] != NULL) ? $feed['profile_media_videos'] : '',
...
```

After:

```php
...
'video' => (isset($feed['profile_media_videos'])) ? $feed['profile_media_videos'] : '',
...
```

## Dependency Injection

For the decoupled and easier to upgrade code in Drupal 8+ Dependency injection should be used instead of calling methods from services statically.

See the Drupal API [Overview of the Dependency Injection Container and Services](https://api.drupal.org/api/drupal/core%21core.api.php/group/container/9.3.x).

Before:

```php
...
$node = Drupal::entityTypeManager()->getStorage('node')->load($result->getField('nid')->getValues()[0]);
...
```

After:

```php
...

$node = $this->entityTypeManager->getStorage('node')->load($result->getField('nid')->getValues()[0]);
...
```

## Creating meaningful log messages

To provide useful logging for site managers, we need to write meaningful log messages with a proper context.

Before:

```php
...
        if($type == 'program') {

          if ($feed['profile_media_videos'] != NULL || $feed['profile_media_images'] != NULL) {
          \Drupal::logger('272')->notice($type);
...
```

After:

```php
...
        if($type == 'program') {

          if ($feed['profile_media_videos'] != NULL || $feed['profile_media_images'] != NULL) {
          \Drupal::logger('form_import')->notice("FORM IMPORT: type is $type");
...
```

# Maintaining an Upgrade Path

All changes in configurations should be added to appropriate hook\_update\_N to update already existing environments. We suggest using the [Config Importer and Tools
](https://www.drupal.org/project/confi) package for working with hook\_update\_N.

## Install files

### `openy.install` in profile

In this file, we should put updates that are related to the distribution in general and don't fit into any feature.

- Enable/Disable module
- General configs

### `openy_*.install` in modules

If you update some configuration for a specific feature, make sure that you put updates into this file in the appropriate module.

## Config Management

### Revert only specific property from config

This is the preferred method of updating configs as it will result in fewer conflicts for upgrading customized YMCA Website Services instances.

With [config_import module](https://www.drupal.org/project/confi) we can update only part of the full config.

For updating specific property in config use the `openy_upgrade_tool.param_updater` service:

1. Find the module where your config lives.
1. Create a new `hook_update_N` in the `openy_*.install` file.
1. In that hook add the update code (for example):

```php
$config = drupal_get_path('module', 'openy_media_image') . '/config/install/views.view.images_library.yml';
$config_importer = \Drupal::service('openy_upgrade_tool.param_updater');
$config_importer->update($config, 'views.view.images_library', 'display.default.display_options.pager');
```

Where:

- `$config` variable contains path to config with config name, like:
- `views.view.images_library` - config name
- `display.default.display_options.pager` - config specific property (you can set value from a nested array with variable depth)

### Revert full configs

This variant uses extensive config file manipulation and increases the time for an upgrade.

For updating full config or several configs from directory use the `openy_upgrade_tool.importer` service:

```php
$config_dir = drupal_get_path('module', 'openy_media_image') . '/config/install';
$config_importer = \Drupal::service('openy_upgrade_tool.importer');
$config_importer->setDirectory($config_dir);
$config_importer->importConfigs(['views.view.images_library']);
```

Where:

- `$config_dir` - path to directory with config
- `views.view.images_library` - config name

Also you can update several configs from a directory:

```php
$config_importer->importConfigs([
  'views.view.images_library',
  'views.view.example_view',
]);
```

# JavaScript includes

![image](https://user-images.githubusercontent.com/563412/122801945-6f28b700-d2cd-11eb-8d0c-694432e8cbf0.png)
