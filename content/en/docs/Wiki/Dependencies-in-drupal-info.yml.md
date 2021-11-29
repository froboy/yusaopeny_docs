In order to generate composer.json Drupal.org defines specific rules in module info.yml file

If you need to add a dependency to the drupal.org module you should provide a format


```yml
dependencies:
  - drupal:webform
```
In this case your module will have composer dependency to https://dgo.to/webform

If you make it

```yml
dependencies:
  - whatevernameyouwish:webform
```
drupal.org packaging routine will replace it with `drupal:webform` on the fly.

In order to break the dependency on composer level but still tell Drupal core to have module dependency while resolving dependencies during the process of enabling module you should use the simplified format below

```yml
dependencies:
  - webform
```
In above case - composer won't have any dependencies, but your module will do require webform module available in a codebase in order to be enabled by drupal core.