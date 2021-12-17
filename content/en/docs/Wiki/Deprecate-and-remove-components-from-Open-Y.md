---
title: Deprecate and remove components from Open Y
---

Occasionally old code is deprecated from the Open Y codebase. In order to minimize disruption to existing sites, we use the following process:

1. **Decide** -  Before removing components from the distribution we gather feedback from the community to protect active projects from having components accidentally removed. This is accomplished via messaging in the Open Y Slack and discussion on Monthly calls.
1. **Deprecate** - Once a decision is made, we notify users that the feature will be removed soon. The deprecated component is moved from the `Open Y` package group to the `Open Y ( Deprecated )` package group. For example: [Deprecate Daxko Program Registration Paragraph](https://github.com/open-y-subprojects/openy_features/pull/15/files). Deprecation notices are posted in point and quarterly releases of Open Y.
1. **Uninstall** - Before removing code, components should be uninstalled via an update hook in the distribution and any hard dependencies should be removed. Uninstalls must occur _at least one point (fix) release_ after the deprecation notice.
1. **Remove** - Complete removal of the component from the codebase or `composer.json` should happen _at least one quarterly (feature) release_ after the deprecation notice.

Additionally, the following housekeeping steps should be taken when deprecating a component:

1. The release where the deprecated component has been uninstalled should be added to the [important versions document](https://github.com/ymcatwincities/openy/wiki/Important-versions-for-upgrade-path) in the Wiki.
1. Code should be decoupled to external GitHub repositories with all history of commits, marked as `openy-decoupled`, and archived.
