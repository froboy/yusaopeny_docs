### OpenY consists from 5 different sub parts

1. OpenY Drupal Profile Distribution https://github.com/ymcatwincities/openy
2. OpenY Project for initiating OpenY instance - https://github.com/ymcatwincities/openy-project
3. Continuous Integration/DevOps for rebuilding/installing OpenY - https://github.com/ymcatwincities/openy-cibox-build
4. CIBox development environment ( Virtualbox, Docker, Vagrant ) https://github.com/ymcatwincities/openy-cibox-vm
5. Docksal development environment - https://github.com/ymcatwincities/openy-docksal ( Docker, Virtualbox )

### Release Management

When tagging a new release of OpenY we used to be doing steps below

1. Review/Merge/Update https://github.com/ymcatwincities/openy-project ( usually composer.json or/and oneline script install ) and tag a new release there
2. Review/Merge all Pull Requests in https://github.com/ymcatwincities/openy that were planned for release
3. Change OpenY version in https://github.com/ymcatwincities/openy/blob/8.x-2.x/openy.info.yml#L5 to expected
3a. Change OpenY version in major modules if there were changes to them ( Activity Finder, PEF, etc ).
4. Create Changelog release notes as a draft and include Contributors as well as major issues fixed/introduced

4a. Spin up a copy of OpenY site and check top priority functionality for regressions.
5. Send for review to core team ( Craig Paulnock, Paige Kiecker ), get approval.
6. Change OpenY version to next with -dev suffix for developers in https://github.com/ymcatwincities/openy/blob/8.x-2.x/openy.info.yml#L5
7. Refresh OpenY private mirror on openy.cibox.tools CI server
8. Check one click install is working https://github.com/ymcatwincities/openy-project/blob/8.2.x/scripts/openyonclickinstall.sh on a fresh DigitalOcean instance 10$ ( 1CPU 2Gb RAM ) . Ensure version of OpenY proper one in site info.
9. Publish announcement in #developers OpenY Slack channel
10. Publish announcement in #general OpenY Slack channel


