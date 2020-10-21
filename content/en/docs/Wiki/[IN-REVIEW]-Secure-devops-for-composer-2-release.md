Composer 2 is coming and older versions of composer 1.x showing now a message

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

If you faced your composer already updated to composer version 2 and having issues with it - downgrade it to latest  1.x version by running a command
```sh
composer selfupdate --1
```