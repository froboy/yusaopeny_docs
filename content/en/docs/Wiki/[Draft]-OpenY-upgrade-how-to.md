Hi, dear OpenY community

This document aims to cover need of upgrade OpenY from older versions to recent ones.

We found the oldest OpenY instance working on 8.0.2 version of OpenY so this document should cover all the way of updating it to the latest version.

### Prepare dedicated environment for upgrade testing

Ensure you have working computer or virtual machine with 
 - Ubuntu 14.04(16.04 or any decent Ubuntu LTS versions) 64 bit
 - MySQL 5.5+
 - Apache 2.4
 - PHP 5.6-7.1 (7.2 is not supported yet)

OpenY team maintains [Vagrant preconfigured Virtualbox based virtual machine with OpenY](https://github.com/ymcatwincities/openy-cibox-vm). Feel free to use it to get working virtual environment.
Your own OpenY instance should have Virtual machine injected into your site codebase. Just find ```Vagrantfile``` and proceed with ```vagrant up``` [accordingly to the documentation](https://github.com/ymcatwincities/openy-cibox-vm/blob/master/README.md).

### Obtain local copy of your production site

You have to create local copy of your site locally to be able to proceed with the upgrade.
For that
 - Make a backup of your production database and copy it to your local machine
 - Make a copy of your production site codebase and copy it to your local machine

...

### Detect version of your OpenY

...

### Run command with next version

...

### Update the site

...

### Check for regressions

...

### Backup current state of the updated site

...

### Proceed with an update to next version until succeeded

...