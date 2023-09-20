---
title: Upgrade use case from 8.2.2.3 to 8.2.7.3
aliases:
  - /docs/wiki/upgrade-use-case-from-8.2.2.3-to-8.2.7.3/
---

This document is archived but may contain useful information for troubleshooting future updates. For updated update steps, visit [How to upgrade YMCA Website Services]({{< relref OpenY-upgrade-how-to-for-Developers.md >}}).

---

1 uninstall `lndr` and `optimizely` modules before running [composer update commands]({{< relref "OpenY-upgrade-how-to-for-Developers#run-command-with-next-never-version--replace-new_version_here-with-the-version-you-are-upgrading-to-eg-8207-" >}})

2 config to remove
```sh

drush cdel image.style.browser_thumbnail
```

3 enable `openy_focal_point` and `media_directories_ui` should be enabled when upgrade from 8.2.2.3 to 8.2.7.3

4 - run drush updatedb [and next steps from tutorial]({{< relref "OpenY-upgrade-how-to-for-Developers#update-the-site" >}})
