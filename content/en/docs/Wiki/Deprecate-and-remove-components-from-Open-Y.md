Welcome to Open Y wiki

In order to remove components, that are outdated or not used by Open Y users we are following policy, described in this document.

1. Before removing components from distribution we need to ensure we are gathering feedback from the community and protecting currently available installation from accidentally removed components, that are still in use. This should be accomplished via messaging in Open Y Slack and discussion on Monthly calls.
2. In order to remove code from Open Y we should deprecate it first in order to notify users it is going to be removed soon. For that components should be moved from `Open Y` package group to `Open Y ( Deprecated )` package group. Example https://github.com/open-y-subprojects/openy_features/pull/15/files . Deprecation notice must be reflected in the upcoming point and quarterly release of Open Y.
3. Before removing a code from distribution component should be uninstalled by adding an upgrade path to distribution. This should happen via Pull Request to second quarterly release after the deprecation notice happened in #2
4. Complete Removal of the component should happen after 2(two) quarterly releases are released since deprecation notice happened ( 6 months minimum ), in next quarterly release since component uninstallation released in a release.
5. Release where uninstallation for deprecated component added should be added to important versions document in Wiki https://github.com/ymcatwincities/openy/wiki/Important-versions-for-upgrade-path
6. Code should be decoupled to external GitHub repositories with all history of commits, marked as `openy-decoupled` and archived. 