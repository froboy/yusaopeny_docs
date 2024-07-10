---
title: How to avoid outdated configuration
linkTitle: avoid outdated configuration
description: Managing config across versions of a module can result in unexpected challenges.
---

Sometimes, in the process of making successive config changes, we need to maintain old config files so that outdated update hooks can still run successfully for sites who are running a module that might be many releases behind.

When a new update runs into an error like:

> Configuration ______ depends on the  ____ configuration that will not exist after import.

the error most often means that some configuration that's expected in a prior update hook has been removed from the codebase.

In order to enable our modules to move quickly and minimize the need for developers to [stop their update process at important versions](../../development/important-versions-for-upgrade-path#important-versions), we have come up with a process of retaining "outdated" configuration when necessary.

## Overview

This process ends up with a configuration directory that looks like:

```shell
config/
|- 1.0/
|--- a.bunch.of.yml
|- 1.3/
|--- some.different.yml
|- install/
|--- the.regular.yml
|- optional/
|--- other.optional.yml
| etc
```

See a few examples:

- [ws_event - MR !72](https://git.drupalcode.org/project/ws_event/-/merge_requests/72)
- [lb_accordion - MR !24](https://git.drupalcode.org/project/lb_accordion/-/merge_requests/24)
- [lb_cards - MR !45](https://git.drupalcode.org/project/lb_cards/-/merge_requests/45)

## Fixing an update hook

1. Find the version of the module where the failing update hook was committed.
2. Checkout or download the old version to a separate working directory.
3. Copy all config files that are being imported in that hook into a new
   directory, like `config/outdated/x.x.x`.
4. Change the `$path` line in the failing update hook, changing
   `/config/optional` to `/config/outdated/x.x.x`.
5. Commit those changes and test thoroughly.

## Warning signs

The error above is the most significant indicator of an issue, but it would be optimal to avoid those errors altogether.

Look out for changes in these types of files:

`core.entity_form_display.block_content.*.default.yml`
`core.entity_view_display.block_content.*.default`

Adding or removing major features or fields could also result in the error.
