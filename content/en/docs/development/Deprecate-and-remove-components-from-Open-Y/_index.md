---
title: Deprecating and removing components
aliases:
  - /docs/wiki/deprecate-and-remove-components-from-open-y/
---

Occasionally old code is deprecated from the YMCA Website Services codebase. In order to minimize disruption to existing sites, we use the following process:

1. **Decide** -  Before removing components from the distribution we gather feedback from the community to protect active projects from having components accidentally removed. This is accomplished via messaging in the YMCA Website Services Slack and discussion on Monthly calls.
2. **Deprecate** - Once a decision is made, we notify users that the feature will be removed soon. The deprecated component is moved from the `YMCA Website Services` package group to the `YMCA Website Services (Deprecated)` package group. For example: [Deprecate Daxko Program Registration Paragraph](https://github.com/open-y-subprojects/openy_features/pull/15/files). Deprecation notices are posted in point and quarterly releases of YMCA Website Services.
3. **Uninstall** - Before removing code, components should be uninstalled via an update hook in the distribution and any hard dependencies should be removed. Uninstalls must occur _at least one point (fix) release_ after the deprecation notice.
4. **Remove** - Complete removal of the component from the codebase or `composer.json` should happen _at least one quarterly (feature) release_ after the deprecation notice.

Additionally, the following housekeeping steps should be taken when deprecating a component:

1. The release where the deprecated component has been uninstalled should be added to the [important versions document](https://github.com/YCloudYUSA/yusaopeny/wiki/Important-versions-for-upgrade-path) in the Wiki.
2. Code should be decoupled to external GitHub repositories with all history of commits, marked as `openy-decoupled`, and archived.

## UX/CX for deprecated components

In order to deliver a high-quality upgrade path and keep the distribution on the bleeding edge of technologies we occasionally replace old and aged components with new ones for a better User eXperience and Content eXperience.

In order to achieve deprecations we have a policy that aims to provide a comfortable migration path for all components of the distribution.

1. When we create a component that will replace an old one we must introduce a period of overlap, when both components are available in the system for some time (6-18 months usually). This allows users to have time and resources to migrate from the old to the new one before it is removed from the distribution. See the [Activity Finder v3 to v4 migration](https://github.com/YCloudYUSA/yusaopeny_activity_finder#update-from-version-3x-to-version-4x).
2. Deprecated components are moved to the deprecated modules group in the list of modules at Admin > Extend. Also, we add [`lifecycle` and `lifecycle_link`](https://www.drupal.org/node/3215042) to the documentation in every deprecated module in order to provide enough information for the community. See [Deprecate openy_gxp.info.yml](https://git.drupalcode.org/project/groupexpro/-/commit/67e7234257abe5f9107f9f5d4a0736e044879dc7).
3. All titles of deprecated components in the Content Editing interface should be renamed to add the suffix `(deprecated)` to help Content Managers on a daily basis to not chose an old component and use a new one. ![Naming Example](<../../../../../assets/img/deprecated_naming.png>)
4. For the majority of content components an automated migration path is expensive and sometimes even impossible, so we have a "lazy migration" practice in our community which puts the responsibility of migration on Content Managers and Strategists. Once new components are available in the distribution all editors should start using them and rebuild old pages by replacing old components with new ones. After the communicated timeframe (6-18 months) old components are removed from the distribution, but if an association needs it the component will be available as an independent—but unsupported—project. It can be supported by a 3rd-party agency or developer as long as it is needed.
5. After the communicated timeframe (6-18 months) the Core team will remove the component from the distribution and keep it in an independent project for archival reasons. Usually, the project is marked as archived/obsolete in order to clarify that it is not supported and is possibly insecure.
6. If the normal timeframe (6-18 months) is not achievable due to unforeseeable circumstances, the Core team will add proper notifications and tutorials for the community to help migrate in a comfortable way in a shorter period of time. See the [GroupEx Pro API deprecation notice](https://ds-docs.y.org/docs/development/daxko/#groupex-pro-apis).
