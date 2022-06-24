---
title: Activity, Class, and Session
---

> These content types format data/content pulled from third parties, such as Daxko, Personify and ActiveNet, for display in Y USA Open Y.

Content editors rarely, if ever, enter information directly into these content types on a day-to-day basis. However, it is important to know how they work and how they relate to manually-entered content.

>**Example - Swim Lessons**
> * Swimming and Aquatics (Program Page, manually entered)
> * Swim Lessons (Program Subcategory Page, manually entered)
> * Youth Group Swim Lessons (Activity, mapped from CRM or custom automation)
> * Stage 3 (Class, mapped from CRM)
> * Monday/Wednesday/Friday 9:30-10 a.m. at Franklin Family YMCA (Session, mapped from CRM)
>
>*Note: This is an example only. Depending on your CRM and any customizations you make, your setup for Swim Lessons or any program may look different that the example listed above.*


## Activity
Often used as the top-level filter in Activity Finder and Repeat Schedules, Activity consists of three fields:

* **Title**: The name of the Activity (and the filter in Activity Finder).
* **Program subcategory**: An *entity reference* to or tag for a [Program Subcategory](https://community.openymca.org/t/program-subcategory-content-types-open-y-user-docs/692). Maps the Activity to higher-levels of user-entered content.
  ***Description:** A description for the Activity. Usually pulled from a description in a CRM through an API.

## Class
A narrower selection of Program Offerings. Not an individual instance, but a smaller selection of instances.

Classes have three ields that map into Activity Finder and Repeat Schedules: a *description*, a *title* and *entity reference/tag* to an Activity.

> Class also contains Areas for content editors to add paragraphs; however, depending on how your CRM and the number of programs your Y runs, it may not be practical use these fields.
## Session
An individual program offering. Contains fields for pricing, session date/time, instructor, ages and a registration link. This are the individual rows/instances in Repeat Schedules and [Activity Finder](https://community.openymca.org/t/activity-finder-activity-finder-search-paragraphs-open-y-user-docs/702).