---
title: How we release OpenY distribution from code perspective
---

### Repos involved in releases

1. Open Y Drupal Profile Distribution [ymcatwincities/openy](https://github.com/ymcatwincities/openy)
1. Open Y Project for initiating an Open Y instance - [ymcatwincities/openy-project](https://github.com/ymcatwincities/openy-project)
1. Continuous Integration/DevOps for rebuilding/installing Open Y - [ymcatwincities/openy-cibox-build](https://github.com/ymcatwincities/openy-cibox-build)
1. CIBox development environment (Virtualbox, Docker, Vagrant) [ymcatwincities/openy-cibox-vm](https://github.com/ymcatwincities/openy-cibox-vm)
1. Docksal development environment (Docker, VirtualBox) - [ymcatwincities/openy-docksal](https://github.com/ymcatwincities/openy-docksal)

### Release Management

When tagging a new release of Open Y, the Lead Architect takes the following steps:

1. Review/Merge/Update [ymcatwincities/openy-project](https://github.com/ymcatwincities/openy-project) (usually composer.json or/and oneline script install) and tag a new release there.
1. Review/Merge all Pull Requests in [ymcatwincities/openy](https://github.com/ymcatwincities/openy) that were planned for release.
1. Change the Open Y version in [`openy.info.yml`](https://github.com/ymcatwincities/openy/blob/9.x-2.x/openy.info.yml#L5).
1. Change the Open Y version in major modules if there were changes to them (Activity Finder, PEF, etc).
1. Create Changelog release notes as a draft and include Contributors as well as major issues fixed/introduced.
1. Spin up a copy of an Open Y site and check top priority functionality for regressions.
1. Send for review to Core Team (Craig Paulnock, Paige Kiecker), get approval.
1. Change the Open Y version to next with -dev suffix for developers in [`openy.info.yml`](https://github.com/ymcatwincities/openy/blob/8.x-2.x/openy.info.yml#L5).
1. Refresh the Open Y private mirror on the `openy.cibox.tools` CI server.
1. Check that the [one-click install](https://github.com/ymcatwincities/openy-project/blob/8.2.x/scripts/openyonclickinstall.sh) is working on a fresh DigitalOcean instance ($10: 1CPU 2Gb RAM). Ensure the version of Open Y is the proper one in site info (`admin/reports/status`).
1. Publish announcement in #developers Open Y Slack channel.
1. Publish announcement in #general Open Y Slack channel.
