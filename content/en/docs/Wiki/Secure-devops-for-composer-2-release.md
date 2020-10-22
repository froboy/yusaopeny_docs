Developer team, partners, and contributors: Composer will be upgraded to 2.x on October 30, 2020,. This could cause issues of instability when your older composer 1.x accidentally auto-updates to the 2.x version due to incompatibility issues. Issues could include: composer fails to run any commands and blocks OpenY upgrade/maintenance. The instability would be in the developer environment, not Open Y/Drupal. 

The Open Y team prepared an avoidance plan for the community to take action steps before the release while Open Y will be verifying Composer 2.x causes no issues or regressions.

If you use Docksal or Vagrant local environments your composer version will not update automatically, so you're currently safe from inadvertent updates. Instructions for updating those environments will be included with any necessary Open Y updates at a later date.

### Case before October 30, 2020, when you are on composer 1.x

Composer 2 is coming and older versions of composer 1.x showing the message below. 

```
Composer 2.0 is about to be released and the older 1.x releases will self-update directly to it once it is released. To avoid surprises update now to the latest 1.x version
```

If you see the message above - ensure your environments have updated composer to the latest 1.x version by running a command
```sh
composer selfupdate --1
```
Ensure the above command shows your version 1.x after an upgrade.
Check the version of composer
```sh
composer --version
```
You should see something like
```sh
MacBook-Pro-Andrii:www podarok$ composer --version
Composer version 1.10.15 2020-10-13 15:59:09
```
as an output of the command.

### If you do not upgrade to the latest 1.x version before October 30, 2020. i.e. if you accidentally upgraded to composer 2.x

If your composer already updated to composer version 2 and you have issues with this upgrade, the solution is to downgrade composer to the latest  1.x version by running the following command.
```sh
composer selfupdate --1
```

If you faced with any issues connect with the Open Y team on GitHub ( [create issue](https://github.com/ymcatwincities/openy/issues/new) ) and the #developers channel [on Slack](https://openy.org/contact) 