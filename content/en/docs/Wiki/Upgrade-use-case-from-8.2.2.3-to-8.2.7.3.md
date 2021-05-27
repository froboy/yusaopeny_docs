

1 uninstall `lndr` and `optimizely` modules before running [composer update commands](https://github.com/ymcatwincities/openy/wiki/OpenY-upgrade-how-to-for-Developers#run-command-with-next-never-version--replace-new_version_here-with-the-version-you-are-upgrading-to-eg-8207-)

2 config to remove
```sh

drush cdel image.style.browser_thumbnail
```

3 enable `openy_focal_point` and `media_directories_ui` should be enabled when upgrade from 8.2.2.3 to 8.2.7.3

4 - run drush updatedb [and next steps from tutorial](https://github.com/ymcatwincities/openy/wiki/OpenY-upgrade-how-to-for-Developers#update-the-site)