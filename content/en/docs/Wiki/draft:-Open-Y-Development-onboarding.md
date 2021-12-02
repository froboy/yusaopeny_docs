In order to work with Open Y developers should follow some basic steps.

# Resources

Open Y core team is managing Sandboxes for stable and development versions of Open Y in order to help with QA and issues investigation.


## Stable Sandboxes

These sandboxes are set to rebuild overnight with every 2 hours DB and assets wipe. In order to get access - visit https://community.openymca.org/t/how-can-i-try-or-get-a-demo-of-open-y/318
These sandboxes contain 3 profile variations
- Standard
- Extended
- Custom
based on the latest stable release of Open Y.

These sandboxes built on CI by running commands
```
composer create-project ymcatwincities/openy-project buildnew --no-interaction --prefer-dist

ansible-playbook docroot/reinstall.yml -i /tmp/inventory5068801741271597001.ini -f 5 -e php_env_vars=APP_ENV=dev -e mysql_user=*** -e mysql_password=*** -e mysql_db=sandbox_carnation_custom -e drupal_folder=/var/www/sandbox_carnation_custom -e site_url=https://sandbox-carnation-cus.openy.org -e pp_environment=demo -e run_reinstall=true -e "openy_profile_install_settings='openy_configure_profile.preset=complete openy_theme_select.theme=openy_carnation'" -e use_solr=false -i localhost, --connection=local -vvvv
```


https://sandboxes.openy.org/

## Development Sandboxes

https://sandboxes-dev.openy.org/
These usually contain the latest 9.x-2.x of Open Y profile. 

These sandboxes built on CI by running commands
```
composer create-project ymcatwincities/openy-project:dev-9.2.x-development buildnew --no-interaction --prefer-dist

ansible-playbook docroot/reinstall.yml -i /tmp/inventory5068801741271597001.ini -f 5 -e php_env_vars=APP_ENV=dev -e mysql_user=*** -e mysql_password=*** -e mysql_db=sandbox_carnation_custom -e drupal_folder=/var/www/sandbox_carnation_custom -e site_url=https://sandbox-carnation-cus.openy.org -e pp_environment=demo -e run_reinstall=true -e "openy_profile_install_settings='openy_configure_profile.preset=complete openy_theme_select.theme=openy_carnation'" -e use_solr=false -i localhost, --connection=local -vvvv
```

## Membership Framework Sandboxes

In order to have QA and demo environments for Membership Framework ( Membership Builder ) Open Y core team hosting and supporting respective sandboxes.

https://membership-framework-sandboxes-d9.openy.org/

They are based on Open Y stable Standard profile and development version of Membership Framework

In order to rebuild the sandbox, CI is running commands

```sh
composer create-project ymcatwincities/openy-project buildnew --no-interaction --prefer-dist
cd buildnew
composer config minimum-stability dev
composer require "openy/openy_memberships":"dev-master as 1.0.0"
ansible-playbook docroot/reinstall.yml -i /tmp/inventory13097841656330601319.ini -f 5 -e php_env_vars=APP_ENV=dev -e mysql_user=*** -e mysql_password=*** -e mysql_db=d9_sandbox_carnation_std_membership_framework -e drupal_folder=/var/www/d9_sandbox_carnation_std_membership_framework -e site_url=https://sandbox-carnation-std-membership-framework-d9.openy.org -e pp_environment=membership_framework -e run_reinstall=true -e "openy_profile_install_settings='openy_configure_profile.preset=standard openy_theme_select.theme=openy_carnation openy_select_content.content=0'" -e use_solr=false -i localhost, --connection=local -vvvv
```

## Activity Finder Sandboxes - development version

- https://sandbox-carnation-cus-d9.openy.org/activity-finder-v4 - Open Y stable, Custom profile, AFv4 dev, Carnation theme, Bootstrap v4
- https://sandbox-rose-cus-d9.openy.org/activity-finder-v4 - Open Y stable, Custom profile, AF v4 dev, Rose theme,  Bootstrap v3
- https://sandbox-lily-cus-d9.openy.org/activity-finder-v4 - Open Y stable, Custom profile, AF v4 dev, Lily theme,  Bootstrap v3

In order to rebuild the sandbox, CI is running commands

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