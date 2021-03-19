Back in 2019 Open Y team started the decoupling process for some major components and projects for them to become independent

Communication started in  [Community Board - decouple thread](https://community.openymca.org/t/ejecting-modules-from-openy-distro-as-independent-projects/513)

After some time a small bunch of projects was decoupled and/or born as decoupled. See [initial index of these projects in wiki](https://github.com/ymcatwincities/openy/wiki/Decoupled-(-external-)-projects-of-OpenY)

In 2021 Open Y core team faced a lot of coupling blocker in Open Y distribution during [the upgrade from Drupal 8 to Drupal 9](https://github.com/ymcatwincities/openy/milestone/21)

In order to make process of decoupling part of Open Y development and maintenance strategy in 2021 Open Y core team shared strategy with wider development community and came to a plan, described in a document [here](https://docs.google.com/presentation/d/1H09GsUsSdt3RoN7rbKpNv4eihCNos74Y2KCbJBJXRqc/edit?usp=sharing)

Down below you can see steps and plan how decoupling should be done in the future

### Policy

- Every new component or sub-project of Open Y should be developed in it's own repository, by using GitHub or Drupal.org project infrastructure. Example of Drupal.org [here](https://www.drupal.org/project/paragraph_skins) and GitHub [here](https://github.com/ymcatwincities/openy_activity_finder)
- The decoupled project **could be part of the core** - e.g [Activity Finder ](https://github.com/ymcatwincities/openy_activity_finder), added to Open Y profile by default, see [here](https://github.com/ymcatwincities/openy/blob/9.2.8.0/composer.json#L112) , or **not part of the core**, e.g. [Open Y Membership Framework](https://github.com/ymcatwincities/openy_memberships) which could be installed additionally by following [this tutorial](https://github.com/ymcatwincities/openy_memberships/blob/master/README.md#installation)
- GitHub should be selected as a repository when there is no strategy to make a component or project available for wider Drupal.org community. When it is tied to YMCA business and unlikely could be leveraged by somebody else
- Drupal.org should be selected as a repository when the component became useful for some other projects, outside of just Open Y. Mandatory requirement here is - component should be able to install on vanilla Drupal without the need of using the Open Y profile.

### Steps for creating a new, decoupled component

- Create a new GitHub/Drupal.org repository
- Work on getting first, finished release with at least `beta` version stability
- create composer.json for the component, in order to be able to start using it via `composer` manager. Example [from Virtual Y](https://github.com/ymcatwincities/openy_gated_content/blob/1.2.4/composer.json)
- Make it available for the public via packagist.org or drupal.org as a release. Ensure `podarok` used added as a co-maintainer to respective system
- Suggest it for adding to Open Y by following the approval process.
- Once approved, create Pull Request with adding it as a dependency in composer.json.
- Ensure this component enabled in any of the Packages, maintained in [Open Y profile installation](https://github.com/ymcatwincities/openy/blob/9.2.8.0/openy.packages.yml) 
- ask for review and release, according to the release plan.

### Steps for decoupling current, existing component of Open Y

- Create a new GitHub/Drupal.org repository
- Filter selected component by running `git filter-branch --subdirectory-filter ...` from the latest development branch of Open Y profile. This is needed as a part of [Code of Conduct](https://github.com/ymcatwincities/openy/wiki/Open-Y-Code-of-Conduct-and-Best-Practices) in order to keep credits of work done for this component.
- create composer.json for the component, in order to be able to start using it via `composer` manager. Example [from Virtual Y](https://github.com/ymcatwincities/openy_gated_content/blob/1.2.4/composer.json)
- Make it available for the public via packagist.org or drupal.org as a release. Ensure `podarok` used added as a co-maintainer to respective system
- Create Pull Request with adding this package back to Open Y profile via composer.json
- Ensure ejected code is not duplicated in Open Y profile. Remove duplicated code in a same Pull Request
- ask for review and release, according to the release plan.