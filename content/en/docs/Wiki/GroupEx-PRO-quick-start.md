For the users, using GroupEx PRO and Schedules integration there is an openy_pef_gxp_sync module created by Open Y team.

In order to configure it, follow steps below


1. Login as Admin
2. Go to Extend (/admin/modules)
3. Install modules `OpenY PEF GXP Sync` and `Open Y Mappings Feature`  and all related (asked on the next step)
4. Go to Open Y -> Integrations -> GroupEx Pro -> GroupEx Pro settings (/admin/openy/integrations/groupex-pro/gxp)
5. Enter Client Id ( obtain this from GroupEx PRO support )
6. Enter Activity (`Group Exercise Classes` (choose node of type Activity from autocomplete). Most likely ID will be 94 if this is a default demo content).
7. Enter Locations Mapping, in the following format, see an example below:
```
202,West YMCA
204,Downtown YMCA
203,East YMCA
3718,South YMCA
```
8. Save configuration
9. Go to the page Configuration -> System -> YMCA Sync settings (/admin/config/system/ymca-sync)
10. Enable checkbox with the label `openy_pef_gxp_sync` and Save configuration. Module openy_pef_gxp_sync should be enabled in your system.
11. Go to the page Open Y -> Settings -> Mappings -> Mapping list (/admin/openy/settings/mappings/mapping)
12. Add mappings for every branch you would like to synchronize:
- Enter the name of the mapping to easily identify it in the future, for instance, `West YMCA GXP sync mapping`
- Authored by keep as is
- Locations - choose Branch
- Groupex ID - Enter GroupEx ID of the Branch
- Save
13. Go to `admin/openy/settings/groupex-enabled-locations` and enable Locations that you want to sync.
14. Run `drush openy-pef-gxp-sync` ( Drupal 8, drush 8 ) or `drush yn-sync openy_pef_gxp_sync.syncer` ( Drupal 9, drush 10 ) command from your project docroot.


See more information about Syncer internals https://github.com/ynorth-projects/openy_pef_gxp_sync#openy-pef-gxp-sync

