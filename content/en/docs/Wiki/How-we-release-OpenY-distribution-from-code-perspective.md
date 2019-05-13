### OpenY consists from 5 different sub parts

1. OpenY Drupal Profile Distribution https://github.com/ymcatwincities/openy
1. OpenY Project for initiating OpenY instance - https://github.com/ymcatwincities/openy-project
1. Continuous Integration/DevOps for rebuilding/installing OpenY - https://github.com/ymcatwincities/openy-cibox-build
1. CIBox development environment ( Virtualbox, Docker, Vagrant ) https://github.com/ymcatwincities/openy-cibox-vm
1. Docksal development environment - https://github.com/ymcatwincities/openy-docksal ( Docker, Virtualbox )

### Release Management

When tagging a new release of OpenY we used to be doing steps below

* Review/Merge/Update https://github.com/ymcatwincities/openy-project ( usually composer.json or/and oneline script install ) and tag a new release there
* Review/Merge all Pull Requests in https://github.com/ymcatwincities/openy that were planned for release
* Change OpenY version in https://github.com/ymcatwincities/openy/blob/8.x-2.x/openy.info.yml#L5 to expected
* Create Changelog release notes as a draft and include Contributors as well as major issues fixed/introduced
* Send for review to core team ( Craig Paulnock, Paige Kiecker ), get approval.
* Change OpenY version to next with -dev suffix for developers in https://github.com/ymcatwincities/openy/blob/8.x-2.x/openy.info.yml#L5
* Refresh OpenY private mirror on openy.cibox.tools CI server
* Check one click install is working https://github.com/ymcatwincities/openy-project/blob/8.2.x/scripts/openyonclickinstall.sh on a fresh DigitalOcean instance 10$ ( 1CPU 2Gb RAM ) . Ensure version of OpenY proper one in site info.
* Publish announcement in #developers OpenY Slack channel
* Publish anouncement in #general OpenY Slack channel


