---
title: Sandboxes
---

# Y USA Open Y Sandboxes for Evaluation and QA

The Y USA Open Y core team manages sandboxes for stable and development versions of Y USA Open Y to facilitate the evaluation of the product, to help with QA, and enable investigation of issues.

To learn more:

- Watch a [detailed video about the process of building the sandboxes](https://www.youtube.com/watch?v=dS-8-t0WJgo)
- Read a [case study on Drupal.org](https://www.drupal.org/case-study/open-y-sandboxes)

## Stable Sandboxes

https://sandboxes.openy.org/

These sandboxes are set to rebuild completely overnight and clear their database and files every 2 hours. To get access visit [How can I try or get a demo of Y USA Open Y?](https://community.openymca.org/t/how-can-i-try-or-get-a-demo-of-open-y/318)

These sandboxes contain 3 profile variations:

- Standard
- Extended
- Custom

based on the latest stable release of Y USA Open Y.

These sandboxes are built on CI by running:

```sh
composer create-project ymcatwincities/openy-project buildnew --no-interaction --prefer-dist

ansible-playbook docroot/reinstall.yml -i /tmp/inventory5068801741271597001.ini -f 5 -e php_env_vars=APP_ENV=dev -e mysql_user=*** -e mysql_password=*** -e mysql_db=sandbox_carnation_custom -e drupal_folder=/var/www/sandbox_carnation_custom -e site_url=https://sandbox-carnation-cus.openy.org -e pp_environment=demo -e run_reinstall=true -e "openy_profile_install_settings='openy_configure_profile.preset=complete openy_theme_select.theme=openy_carnation'" -e use_solr=false -i localhost, --connection=local -vvvv
```

## Development Sandboxes

https://sandboxes-dev.openy.org/

These usually contain the latest development version of Y USA Open Y (the master branch of [openy](https://github.com/ymcatwincities/openy).

These sandboxes are built on CI by running:

```sh
composer create-project ymcatwincities/openy-project:dev-9.2.x-development buildnew --no-interaction --prefer-dist

ansible-playbook docroot/reinstall.yml -i /tmp/inventory5068801741271597001.ini -f 5 -e php_env_vars=APP_ENV=dev -e mysql_user=*** -e mysql_password=*** -e mysql_db=sandbox_carnation_custom -e drupal_folder=/var/www/sandbox_carnation_custom -e site_url=https://sandbox-carnation-cus.openy.org -e pp_environment=demo -e run_reinstall=true -e "openy_profile_install_settings='openy_configure_profile.preset=complete openy_theme_select.theme=openy_carnation'" -e use_solr=false -i localhost, --connection=local -vvvv
```

## Membership Framework Sandboxes

https://membership-framework-sandboxes-d9.openy.org/

These are based on the Y USA Open Y stable Standard profile and the development version of the [Membership Framework](https://github.com/ymcatwincities/openy_memberships).

To rebuild the sandbox, CI is running:

```sh
composer create-project ymcatwincities/openy-project buildnew --no-interaction --prefer-dist
cd buildnew
composer config minimum-stability dev
composer require "openy/openy_memberships":"dev-master as 1.0.0"
ansible-playbook docroot/reinstall.yml -i /tmp/inventory13097841656330601319.ini -f 5 -e php_env_vars=APP_ENV=dev -e mysql_user=*** -e mysql_password=*** -e mysql_db=d9_sandbox_carnation_std_membership_framework -e drupal_folder=/var/www/d9_sandbox_carnation_std_membership_framework -e site_url=https://sandbox-carnation-std-membership-framework-d9.openy.org -e pp_environment=membership_framework -e run_reinstall=true -e "openy_profile_install_settings='openy_configure_profile.preset=standard openy_theme_select.theme=openy_carnation openy_select_content.content=0'" -e use_solr=false -i localhost, --connection=local -vvvv
```

## Activity Finder Sandboxes - development version

| Theme | Link | Y USA Open Y | Profile | Activity Finder | Theme | Bootstrap |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Carnation | https://sandbox-carnation-cus-d9.openy.org/activity-finder-v4 | stable | Custom | v4 dev | v4 |
| Rose | https://sandbox-rose-cus-d9.openy.org/activity-finder-v4 | stable |  Custom | v4 dev | v3 |
| Lily | https://sandbox-lily-cus-d9.openy.org/activity-finder-v4 | stable | Custom | v4 dev | v3 |

To rebuild the sandbox, CI is running:

```sh
composer create-project ymcatwincities/openy-project:dev-9.2.x-development-af4 build --no-interaction --prefer-dist
cd ${WORKSPACE}/build
composer require ymcatwincities/openy_activity_finder:"4.x-dev as 4.0"

ansible-playbook docroot/reinstall.yml -i /tmp/inventory4660848605526222353.ini -f 5 -e php_env_vars=APP_ENV=dev -e mysql_user=*** -e mysql_password=*** -e mysql_db=d9_sandbox_carnation_custom -e drupal_folder=/var/www/d9_sandbox_carnation_custom -e site_url=https://sandbox-carnation-cus-d9.openy.org -e pp_environment=demo -e run_reinstall=true -e "openy_profile_install_settings='openy_configure_profile.preset=complete openy_theme_select.theme=openy_carnation'" -i localhost, --connection=local -vvvv

# Solr 4.5-4.9, Activity Finder v4
drush en -y search_api_solr_legacy openy_prgf_activity_finder_4 || true
drush cset -y search_api.server.solr backend_config.connector_config.host 127.0.0.1 -y || true
drush cset -y search_api.server.solr backend_config.connector_config.core ${VHOST_FOLDER} -y
drush cset -y search_api.server.solr backend_config.connector_config.solr_version 4.5 -y
drush search-api-mark-all || true
drush sapi-i || true
drush en -dvy openy_prgf_af4_demo || true

# Solr 4.5-4.9, Activity Finder v4, Carnation theme, bootstrap v4
drush cset -y openy_activity_finder.settings bs_version 4 || true

```
