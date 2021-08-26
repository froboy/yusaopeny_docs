# Welcome to Open Y wiki

## Preamble

Back in 28 Jan 2020 Open Y decided to add an anonymous analytics module https://github.com/ymcatwincities/openy/tree/9.x-2.x/modules/custom/openy_analytics which was a free opt-in/opt-out solution for the Core team to gather stats from Open Y sites about the frequency of components used. 
The idea behind this was to gather data in order to understand the demand for the components in Open Y and make decisions based on this data.

Due to recent information this feature is not frequently used, the Open Y Core team decided to sunset this functionality and remove openy_analytics as well as openy_update modules from the Open Y Distribution in order to reduce server load from Open Y instances and archive the analytics server as deprecated.

## How to opt-out from analytics subsystem

Visit `OpenY\Terms and conditions` in your Open Y site instance and uncheck Optional Permissions checkbox

![image](https://user-images.githubusercontent.com/563412/130236284-5979a4fe-289c-4ccc-9c18-059d17d143e8.png)

After submitting this form your site will stop sending anonymous data.
If the checkbox was not enabled - just disregard it, you didn't opt-in earlier

# Deprecation action
Uninstall and deprecation was done in https://github.com/ymcatwincities/openy/pull/2537