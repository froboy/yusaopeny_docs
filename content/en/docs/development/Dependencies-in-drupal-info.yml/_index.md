---
title: Dependencies in drupal info.yml
aliases:
  - /docs/wiki/dependencies-in-drupal-info.yml/
---

In order to generate `composer.json`, Drupal.org defines specific rules in the modules `info.yml` file

If you need to add a dependency to the Drupal.org module you should provide a format:

```yml
dependencies:
  - drupal:webform
```

In this case, your module will have composer dependency to [drupal/webform](https://dgo.to/webform)

If you make it:

```yml
dependencies:
  - whatevernameyouwish:webform
```

the Drupal.org packaging routine will replace it with `drupal:webform` on the fly.

In order to break the dependency on composer level but still tell Drupal core to have module dependency while resolving dependencies during the process of enabling the module, you should use the simplified format:

```yml
dependencies:
  - webform
```

In the above case, composer won't have any dependencies, but your module will require that the webform module be available in the codebase in order to be enabled by Drupal core.
