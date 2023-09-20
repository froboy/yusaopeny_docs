---
title: Decoupling components as independent modules
aliases:
  - /docs/wiki/decouple-component-from-open-y-as-independent-module-project/
---

## History

In 2019 the YMCA Website Services team started decoupling major components to streamline the distribution and simplify support.

Communication started in the Community Board - Ejecting modules from OpenY distro as independent projects.

The decoupling process is ongoing. See [the index of decoupled projects]({{< relref "Decoupled-(-external-)-projects-of-OpenY" >}}).

In 2021 the YMCA Website Services core team faced coupling blockers in the distribution during [the upgrade from Drupal 8 to Drupal 9](https://github.com/YCloudYUSA/yusaopeny/milestone/21)

To formalize the ongoing development and maintenance strategy, the YMCA Website Services core team [shared its decoupling plan with the wider community](https://docs.google.com/presentation/d/1H09GsUsSdt3RoN7rbKpNv4eihCNos74Y2KCbJBJXRqc/edit?usp=sharing) in mid-2021.

This document elaborates on those processes.

## Policy

- Every new component or sub-project of YMCA Website Services should be developed in its own repository - either on GitHub or Drupal.org.
  - Drupal.org example: [paragraph_skins](https://www.drupal.org/project/paragraph_skins)
  - GitHub Example: [openy_activity_finder](https://github.com/YCloudYUSA/yusaopeny_activity_finder)
- The decoupled project could be
  - **part of YMCA Website Services core** - e.g. [Activity Finder](https://github.com/YCloudYUSA/yusaopeny_activity_finder) and [added to YMCA Website Services profile by default](https://github.com/YCloudYUSA/yusaopeny/blob/9.2.8.0/composer.json#L112), or
  - **not part of the core**, e.g. [YMCA Website Services Membership Framework](https://github.com/YCloudYUSA/yusaopeny_memberships) which could be [installed later](https://github.com/YCloudYUSA/yusaopeny_memberships/blob/master/README.md#installation).
- **GitHub** should be used when there is no strategy to make a component or project available for the wider Drupal community - that is, when it is tied to YMCA business and unlikely to be leveraged by somebody else.
- **Drupal.org** should be used when the component could be useful to projects outside of YMCA Website Services.

## Process

### for creating a new decoupled component

1. Create a new GitHub/Drupal.org repository.
1. Work on getting an initial release with at least `beta` version stability.
1. Create a composer.json file for the component in order to be able to start using it via `composer`. See [Virtual Y](https://github.com/YCloudYUSA/yusaopeny_gated_content/blob/master/composer.json) for an example.
1. Make it available for the public via packagist.org or drupal.org as a release. Ensure `podarok` is added as a co-maintainer to the respective system.
1. Suggest adding to YMCA Website Services by [opening an issue](https://github.com/YCloudYUSA/yusaopeny/issues).
1. If approved, create a Pull Request adding it as a dependency in [composer.json](https://github.com/YCloudYUSA/yusaopeny/blob/9.x-2.x/composer.json).
1. Ensure this component is enabled in any of the packages maintained in the [YMCA Website Services profile installation](https://github.com/YCloudYUSA/yusaopeny/blob/9.x-2.x/openy.packages.yml)
1. Ask for review and release, according to the [release plan]({{< relref "How-we-release-OpenY-distribution-from-code-perspective" >}}).

### for decoupling an existing component of YMCA Website Services

Follow the steps above, but:

- After creating the repo, filter the selected component by running `git filter-branch --subdirectory-filter ...` from the latest development branch of the YMCA Website Services profile. This keeps credits of work done for this component as a part of the [Code of Conduct]({{< relref "Open-Y-Code-of-Conduct-and-Best-Practices" >}}).
- After separating the code, ensure the ejected code is not duplicated in the YMCA Website Services profile. Remove duplicated code in the same Pull Request in which you add the new dependency.

## Examples

### How to update module on Drupal.org

- Git filter-branch to get a history of changes.
- Change git origin to Drupal.org project.
- Create a new branch and push the code to Drupal.org.
- Create and push tag to Drupal.org. Create a release on drupal.org.
- Update composer.json in this distribution with a new tag.

### How to decouple module from YN to Drupal.org

Example: [paragraph_skins](https://www.drupal.org/project/paragraph_skins)

```sh
git clone git@github.com:YCloudYUSA/yusaopeny.git decouple
rm -rf decouple_copy && cp -a decouple decouple_copy
cd decouple_copy
git filter-branch --subdirectory-filter docroot/modules/contrib/paragraph_skins
git clean -dfx
git remote remove origin && git remote add origin git@git.drupal.org:project/paragraph_skins.git
git pull origin 8.x-1.x --allow-unrelated-histories
# Resolve conflicts if applicable.
git push origin production:8.x-1.x
# Create tags and release on Drupal.org
```

### How to decouple module from YMCA Website Services to [YMCA Website Services Subprojects](https://github.com/Open-Y-subprojects)

Request a repository for the module. Example: [shared_content_server](https://github.com/Open-Y-subprojects/shared_content_server)

```sh
git clone git@github.com:YCloudYUSA/yusaopeny.git decouple
rm -rf decouple_copy && cp -a decouple decouple_copy
cd decouple_copy
git filter-branch --subdirectory-filter docroot/profiles/contrib/openy/modules/custom/SOME_MODULE_HERE
git clean -dfx
git remote remove origin && git remote add origin git@github.com:Open-Y-subprojects/SOME_MODULE_HERE.git
git push origin production
# Create composer.json on the decoupled repository. Example: https://github.com/YCloudYUSA/yusaopeny_activity_finder/blob/4.x/composer.json
git clone git@github.com:ynorth-projects/distribution.git yn-distribution
# Update composer json for distrubution. See below
```

[Example for Activity Finder](https://github.com/YCloudYUSA/yusaopeny/pull/2288/files#diff-d2ab9925cad7eac58e0ff4cc0d251a937ecf49e4b6bf57f8b95aab76648a9d34R111)

# References

- A useful article for future decoupling - [Move files from one repository to another, preserving git history](https://medium.com/@ayushya/move-directory-from-one-repository-to-another-preserving-git-history-d210fa049d4b)
