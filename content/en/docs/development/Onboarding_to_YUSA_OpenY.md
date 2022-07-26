# Welcome to YMCA Code Sharing 


## List of migrated repositories/projects

- Open Y  https://github.com/YCloudYUSA/yusaopeny
- Virtual Y https://github.com/YCloudYUSA/yusaopeny_gated_content
- Activity Finder https://github.com/YCloudYUSA/yusaopeny_activity_finder
- Membership Framework https://github.com/YCloudYUSA/yusaopeny_memberships
- Open Y Docs https://github.com/YCloudYUSA/yusaopeny_docs
- Open Y project https://github.com/YCloudYUSA/yusaopeny-project

## How to start developing Open Y

In order to get copy of latest development version of Open Y, please follow steps from YUSA OpenY README.md
See https://github.com/YCloudYUSA/yusaopeny/blob/9.x-2.x/README.md#latest-development-version-drupal-9-2x

Pay attention Open Y has a modular structure, so if you plan changes to specific component - create Pull Request/Merge Request in respective project or repository, based on component's composer.json data.

In order to test specific component - create PR to Open Y https://github.com/YCloudYUSA/yusaopeny/pulls with adding reference in composer.json of Open Y in order for the build system to start using updated component.

### QA sandboxes for Open Y

See case study of sandboxes https://www.drupal.org/case-study/open-y-sandboxes

- https://sandboxes-dev-php8.openy.org/ - PHP 8.1 and Latest Open Y development branch ( 9.x-2.x from https://github.com/YCloudYUSA/yusaopeny )
- https://sandboxes-dev.openy.org/ - PHP 7.4 and Latest Open Y stable release ( from https://github.com/YCloudYUSA/yusaopeny )

## How to start developing Virtual Y

See https://github.com/YCloudYUSA/yusaopeny_gated_content#development

### QA sandboxes for Virtual Y

- https://virtual-y-sandboxes-d9.openy.org/ on development version of Open Y, development version of VY
- https://virtual-y-sandboxes.openy.org/ - on stable version of Open Y, stable version if VY

## How to start developing Membership Framework

See how to install/build it to your Open Y working project https://github.com/YCloudYUSA/yusaopeny_memberships/blob/master/README.md#installation


### QA sandboxes for MF

- https://membership-framework-sandboxes-d9.openy.org/ - on development version of Open Y, development version of MF 
- https://membership-framework-sandboxes.openy.org/ - on stable version of Open Y, stable version of MF

## How to start developing Activity Finder

Activity Finder is part of Open Y - so same process.

### QA Sandboxes for Activity Finder

- https://sandbox-lily-cus-d9.openy.org/ - Lily Theme, Open Y Custom
- https://sandbox-rose-cus-d9.openy.org/ - Rose Theme, Open Y Custom
- https://sandbox-carnation-cus-d9.openy.org/ - Carnation Theme, Open Y Custom
