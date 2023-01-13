---
title: Deprecate and remove components from YMCA Website Services
---

Occasionally old code is deprecated from the YMCA Website Services codebase. In order to minimize disruption to existing sites, we use the following process:

1. **Decide** -  Before removing components from the distribution we gather feedback from the community to protect active projects from having components accidentally removed. This is accomplished via messaging in the YMCA Website Services Slack and discussion on Monthly calls.
2. **Deprecate** - Once a decision is made, we notify users that the feature will be removed soon. The deprecated component is moved from the `YMCA Website Services` package group to the `YMCA Website Services ( Deprecated )` package group. For example: [Deprecate Daxko Program Registration Paragraph](https://github.com/open-y-subprojects/openy_features/pull/15/files). Deprecation notices are posted in point and quarterly releases of YMCA Website Services.
3. **Uninstall** - Before removing code, components should be uninstalled via an update hook in the distribution and any hard dependencies should be removed. Uninstalls must occur _at least one point (fix) release_ after the deprecation notice.
4. **Remove** - Complete removal of the component from the codebase or `composer.json` should happen _at least one quarterly (feature) release_ after the deprecation notice.

Additionally, the following housekeeping steps should be taken when deprecating a component:

1. The release where the deprecated component has been uninstalled should be added to the [important versions document](https://github.com/YCloudYUSA/yusaopeny/wiki/Important-versions-for-upgrade-path) in the Wiki.
2. Code should be decoupled to external GitHub repositories with all history of commits, marked as `openy-decoupled`, and archived.


## UX/CX for deprecated components

In order to deliver high quality upgrade path and keep YMCA Website Services distribution on a bleeding edge of technologies we were/are/will be removing old and aged components in favor of introducing decent for better User eXperience and Content eXperience of our community.

In order to achive deprecations we have a policy which aims to serve comfortable migration path for all pieces of distribution.

1. When we create component, which will replace old one in a distribution we must introduce overlap, when both components available in a system for some time ( 6-18 months usually ) in order for users have time and resources to switch anbd migrate from old to new one, before removing it from the distribution. Example - Activity Finder v4 and v3.
2. Deprecated components should be moved to deprected module's group in Admin Extend dashboard. Also we need to add lifecycle status and information url to documentation in every deprecated module in order to provide enough information for the community. Example https://git.drupalcode.org/project/groupexpro/-/commit/67e7234257abe5f9107f9f5d4a0736e044879dc7
3. All titles of the deprecated component in Content Editing interface should be renamed to add suffix `(deprecated)` in order to help Content Managers on a daily basis to not chose old component and use a new one. [Naming Example](<../../../../../assets/img/deprecated_naming.png>)
4. For majority content components automated migration path is expencive and sometimes even impossible, so we have "lazy migration" practice in our community which puts responsibility for migration on shoulders of Content Managers and Strategists. Once new components is available in distribution all editors should start using it and rebuild old pages by replacing old components with the new. After communicated timeframe ( 6-18 months ) old component is removed from the distribution, but if association needs it, component will be available as a independent, but unsupported by Core team project. It can be supported by 3rd party agency or developer until it would be needed.
5. After communicated timeframe ( 6-18 months ) Core team will remove component from distribution and keep it in independent project for archival reasons. Usually project marked as archived/obsolete in order to give clear message it is not supported and most likely unsecure.
6. If normal timeframe ( 6-18 months ) is not achievable because of force majour reasons, Core team adds proper notifications and tutorials for the community to be able to migrate in a comfortable way in a shorter period of time. Example https://ds-docs.y.org/docs/development/daxko/#groupex-pro-apis
