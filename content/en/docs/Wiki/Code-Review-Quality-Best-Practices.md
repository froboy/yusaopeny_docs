In order to deliver high quality code and product for Open Y users we are relying on [Code of Conduct and Best Practices](https://github.com/ymcatwincities/openy/wiki/Open-Y-Code-of-Conduct-and-Best-Practices).
Current document is more technical in depth for specific cases that were discussed during long time code quality review process Open Y team has in place, where all code should be reviewed by 1-2 developers before merging into Open Y codebase.

Generic Rules
=====

It is almost impossible to create a reusable module when you'll grab altogether new features and content types, unrelated to them. Or settings, related to only this project. That's why all settings(features in the Drupal world) should be split out of the module, tied to. 

1. OpenY naming convention

    1. Features module naming

        1. **openy_${entity_type|abbr}_${entity_bundle|abbr}_${feature|optional}**

            1. Example: **openy_node_blog_feature**

            2. **openy_prgf_sc_feature** -> OpenY Paragraph Simple Content (name within yml)

    2. Fields naming (<=20 chars)

        2. **field_${entity_type|abbr}_${entity_bundle|abbr}_{name|abbr}**

            3. Example: **field_prgf_sc_body**

    3. **All descriptions mandatory!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!**

2. Modules naming. Depending to the context we should chose the name from below list

    4. **${project_name|abbr}_${business_name|abbr**} - when the code looks like legacy and has specifics not ready to be open source

    5. **openy_${business_name|abbr} **- when the code is ready to be ejected to OpenY package

    6. **${business_name}** - when the code is so abstract that it has no tying to OpenY, and ready to be hosted on Drupal.org as independet project.


Code sharing
=====

For ability to support code sharing MODULE-NAME should be selected in relation to business logic of the module. It is not good to create modules by abstracting it out of the business. All the modules, ejected to drupal.org from our past project were possible to share only because they represent some feature, tied to a business. 
Like 
- personify - module for SOAP related methods for working with Personify API
- acrypt - Asymetric crypt alghoritm

and so on.

PHP
=====

Return early pattern
====

To keep readability in functions and methods, it is wise to return early if simple conditions apply that can be checked at the beginning of a method:

```php
<?php

function foo($bar, $baz)
{
    if ($foo) {
        //assume
        //that
        //here
        //is
        //the
        //whole
        //logic
        //of
        //this
        //method
        return $calculated_value;
    } else {
        return null;
    }
}
?>
```
It's better to return early, keeping indentation and brain power needed to follow the code low.

```php
<?php

function foo($bar, $baz)
{
    if (!$foo) {
        return null;
    }

    //assume
    //that
    //here
    //is
    //the
    //whole
    //logic
    //of
    //this
    //method
    return $calculated_value;
}
?>
```

Define early pattern
=====

When you have a condition that aims to change the value of variable without additional logic, get rid of ```if else elseif``` code, just define early variable and change it via conditions

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

# How to support upgrade path
All changes in configurations should be added to appropriate hook\_update\_N in order to update already existing environments. We suggest to use https://www.drupal.org/project/confi for working with hook\_update\_N.

### `openy.install` in profile
In this file we should put updates that are related to the distribution in general and don't fit into any feature.

- Enable/Disable module
- General configs

### `openy_*.install` in modules
In case if you update some configuration for specific feature, make sure that you put updates into appropriate module.

### Revert only specific property from config
This is preffered method of updating configs due to less conflicts for upgrading customized Open Y instances 

With [config_import module](https://www.drupal.org/project/confi) help we can update only part from full config.

For updating specific property in config (use service 'openy_upgrade_tool.param_updater'):

1) go to related to this config module

2) create new hook_update_N in openy_*.install file

3) in update add next code (this is example):

```
$config = drupal_get_path('module', 'openy_media_image') . '/config/install/views.view.images_library.yml';
$config_importer = \Drupal::service('openy_upgrade_tool.param_updater');
$config_importer->update($config, 'views.view.images_library', 'display.default.display_options.pager');
```
Where:
- $config variable contains path to config with config name
- "views.view.images_library" - config name
- "display.default.display_options.pager" - config specific property (you can set value from a nested array with variable depth)

### Revert full configs
Keep in ming this variant has an extensive config files manipulation and increases time for upgrade.

For updating full config or several configs from directory use service 'openy_upgrade_tool.importer'.
```
$config_dir = drupal_get_path('module', 'openy_media_image') . '/config/install';
$config_importer = \Drupal::service('openy_upgrade_tool.importer');
$config_importer->setDirectory($config_dir);
$config_importer->importConfigs(['views.view.images_library']);
```
Where:
- $config_dir - path to directory with config
- "views.view.images_library" - config name


Also you can update several configs from directory:
```
$config_importer->importConfigs([
  'views.view.images_library',
  'views.view.example_view',
]);
```

### JavaScript includes
![image](https://user-images.githubusercontent.com/563412/122801945-6f28b700-d2cd-11eb-8d0c-694432e8cbf0.png)
