There are plenty of [YAML](http://en.wikipedia.org/wiki/YAML) configuration files in the root of the profile. Some of them are standard Drupal configuration and others are Open Y specific.

## Basic .yml files
The following ones are very common and can be found in many Drupal modules:
* openy.info.yml ([documentation](https://www.drupal.org/docs/8/creating-custom-modules/let-drupal-8-know-about-your-module-with-an-infoyml-file)) - defines Open Y as a profile, defines its name and dependecies
* openy.libraries.yml ([documentation](https://www.drupal.org/docs/8/creating-custom-modules/adding-stylesheets-css-and-javascript-js-to-a-drupal-8-module)) - defines global Open Y drupal asset libraries
* openy.permissions.yml - defines global Open Y permissions
* openy.services.yml ([documentation](https://www.drupal.org/docs/8/api/services-and-dependency-injection/structure-of-a-service-file)) - if you are introducing a service that is needed by all (or majority of) Open Y modules add it here and store the service class file at `openy/src` directory

## Open Y specific .yml files
There are also a few configurations related to Open Y installation process and Open Y package system:
* openy.installation_types.yml
* openy.themes.yml
* openy.packages.yml

### Open Y packages
Open Y package system introduces a new level of abstraction shifting from Drupal standard module level to packages. Packages represent complete Open Y features, which usually aren't a single module and it could be hard to identify all needed modules if a developer isn't familiar with Open Y. A package is just a group of several modules. You can enable and disable a package, this means the whole set of the associated Drupal modules are enabled or disabled.

The approach provides a convenient and easy way of managing Open Y features.

Open Y system module provides a page where enabled and available packages are listed and can be installed/uninstalled. See `/admin/openy/extend` page.



### Open Y Installation types
When an Open Y site is installed there is also another abstraction level - an installation type. This thing groups packages.

So the hierarchy is following:
* installation type
  * package
    * module
    * module
  * package
    * module
    * module
    * module
  * package
    * module
* installation type
  * package
    * module

### openy.installation_types.yml
`openy.installation_types.yml` defines the high level presets available during website installation.

File structure:
```
standard:
  name: Standard
  packages:
    - alerts
    - editorial
    - news
    - seo
    - webform

extended:
  name: Extended
  packages:
    - alerts
    - analytics
    - ...

complete:
  name: Complete/Developer
  hidden: true
  packages:
    - activenet
    - ...
```

Each installation type has a machine name which is a key of the top-level items.

#### Properties of installation types:
 - **name** (required) - defines a human-friendly name of the installation type
 - **packages** (required) - a list of Open Y packages that are associated with the installation type. The packages are listed when a website is installed via web-interface 
 - **hidden** (optional) - dictates if the installation type must be hidden when a website is installed via web interface

If an Open Y site is installed using web-interface there is a step where the installation type can be selected (pic)

If an Open Y site is installed using drush then the installation type can be specified by an optional argument for the `drush site-install` command ([Installation with Drush](https://github.com/ymcatwincities/openy/blob/8.x-2.x/docs/Development/InstallationWithDrush.md)):
```
  drush site-install openy /
     --db-url="mysql://user:pass@host:3306/db" /
     --root=/docroot /
     openy_configure_profile.preset=extended
```


### openy.packages.yml
Packages are defined in `openy.packages.yml`. This file is placed in the root of the profiles, it's automatically detected and used by Open Y installation process.

File structure
```
blog:
  name: 'Blog'
  description: "Blog package provides a set of modules to maintain and create different blog post listings."
  help: '<p>Using Blog package you can create and maintain blog posts and create flexible listings of blog posts. Watch a video below to learn more about blog anatomy.</p>
  <iframe width="560" height="315"
               src="https://www.youtube.com/embed/PTZkgOb8CFE"
               frameborder="0" allow="autoplay; encrypted-media"
               allowfullscreen></iframe>'
  modules:
    - openy_node_blog
    - openy_prgf_blog_listing
    - openy_prgf_featured_blogs
    - openy_prgf_blog_branch
    - openy_prgf_blog_camp
    - openy_prgf_blog_latest
    - openy_txnm_blog_category

camps:
  name: 'Camps'
  description: "Camps package provides a set of modules to maintain camps and add them to the location finder page."
  help: '<p>Using Camps package you can create and maintain Camps and extend location finder page to include them.</p>'
  modules:
    - openy_prgf_camp_menu
    - openy_loc_camp
```

Each package has a machine name which is a key of the top-level items.

#### Properties of packages:
 - **name** (required) - defines a human friendly name of the package.
 - **description** (required) - a short explanation of the package features. It's shown on the Open Y dashboard.
 - **help** (required) - an HTML markup with the help message that appears on the installation via web-interface when the help icon is hovered.
 - **modules** (required) - a list of Drupal modules that are associated with the package. When the package is installed/uninstalled the associated modules are installed/uninstalled respectively.

_Provide images that show properties in action_

/admin/openy/extend

### openy.theme.yml
The file defines which of Open Y themes are available when a website is installed.

If an Open Y site is installed using Drush then the theme can be specified by an optional argument for the `drush site-install` command ([Installation with Drush](https://github.com/ymcatwincities/openy/blob/8.x-2.x/docs/Development/InstallationWithDrush.md)):
```
  drush site-install openy /
    --db-url="mysql://user:pass@host:3306/db" /
    --root=/docroot /
    openy_configure_profile.preset=extended /
    openy_theme_select.theme=openy_rose
```
