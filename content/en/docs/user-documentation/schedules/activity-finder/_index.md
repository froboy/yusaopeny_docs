---
title: Activity Finder
description: Provides an interactive tool to help members find and book activities.
tags:
  - "Decoupled Applications"
  - "Activity Finder"
---

Activity Finder combines data from [the Activity, Class, and Session](../../content-types/activity-class-session) content types into an interactive tool that can be used with [Paragraphs](../../paragraphs/activity-finder) or [Layout Builder](../../layout-builder/activity-finder) pages.

Out-of-the-box, YMCA Website Services’s Activity Finder integrates with [Daxko](https://www.daxko.com/), [ActiveNet](https://www.activenetwork.com/activenet), and [Personify](https://personifycorp.com/solutions/ymcas-and-jccs/). Configuring these integrations is mostly user-friendly, but often is supported by a partner development team. Any other CRM will require custom developer work.

See the [Program Event Framework developer docs](../../../development/program-event-framework) for a full list of integrations.

## Additional topics

### Allowing UTM codes in Activity Finder

[UTM codes](https://en.wikipedia.org/wiki/UTM_parameters) can be used to track the effectiveness of marketing campaigns. Activity Finder uses query strings as filters, but as of [version 4.2.0](https://github.com/YCloudYUSA/yusaopeny_activity_finder/releases/tag/4.2.0) it will also maintain UTM codes in the URL.

Activity Finder begins with a number of preset arguments, and those can be modified at **Admin** > **YMCA Website Services** > **Settings** > **Activity Finder Settings** (`/admin/openy/settings/activity-finder`) in the **Allowed Query Arguments** field.

![A screenshot of the Activity Finder settings, focused on the "Allowed Query Arguments" field](activity-finder--utm-codes.png)

Once those settings are saved, you can visit an Activity Finder page with UTM codes attached, for example:

`https://example.com/activity_finder?step=results&selectedAges=24&selectedLocations=1541437&selectedActivities=2786027,2786083&utm_source=promotional_member&utm_medium=email&utm_content=button_register_now&utm_campaign=fall_group_swim_lessons_2021`

and see that the codes are maintained as the filters are changed.
