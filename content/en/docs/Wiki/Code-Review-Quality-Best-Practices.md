In order to deliver high quality code and product for Open Y users we are relying on [Code of Conduct and Best Practices](https://github.com/ymcatwincities/openy/wiki/Open-Y-Code-of-Conduct-and-Best-Practices).
Current document is more technical in depth for specific cases that were discussed during long time code quality review process Open Y team has in place, where all code should be reviewed by 1-2 developers before merging into Open Y codebase.

Generic Rules
=====

It is almost impossible to create a reusable module when you'll grab altogether new features and content types, unrelated to them. Or settings, related to only this project. That's why all settings(features in the Drupal world) should be split out of the module, tied to. 

1. OpenY naming convention

    1. Features module naming

        1. **openy_${entity_type|abbr}_${entity_bundle|abbr}_${feature|optional}**

            1. Example: **openy_node_blog_feature**

            2. **openy_prgf_sc_feature** -> OpenY Paragraph Simple Content (name within yml)

    2. Fields naming (<=20 chars)

        2. **field_${entity_type|abbr}_${entity_bundle|abbr}_{name|abbr}**

            3. Example: **field_prgf_sc_body**

    3. **All descriptions mandatory!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!**

2. Modules naming. Depending to the context we should chose the name from below list

    4. **${project_name|abbr}_${business_name|abbr**} - when the code looks like legacy and has specifics not ready to be open source

    5. **openy_${business_name|abbr} **- when the code is ready to be ejected to OpenY package

    6. **${business_name}** - when the code is so abstract that it has no tying to OpenY, and ready to be hosted on Drupal.org as independet project.


