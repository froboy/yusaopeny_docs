---
title: Activity Finder Security Notice
date: 2023-04-18
description: Trusted hosts settings are now required for sites that use Activity Finder.
---

## Summary

Activity Finder could provide an attack vector where a malicious site could use the “trusted” YMCA domain to redirect users to an untrusted site.

Sites using Activity Finder should immediately ensure they have `activity_finder_trusted_redirect_host_patterns` configured in settings.php as per [the documentation](https://github.com/YCloudYUSA/yusaopeny_activity_finder#trusted-redirect-host-patterns) and update to the [latest release of Activity Finder](https://github.com/YCloudYUSA/yusaopeny_activity_finder/releases/).

## What is the problem?

[Activity Finder](https://github.com/YCloudYUSA/yusaopeny_activity_finder) provides a method for sites to redirect users to register for activities. The method passes a URL in a query string, like `exampleymca.org/af/register-redirect/1234?url=https://exampleactivities.com...`. 

Activity Finder provides a method to [only allow trusted hosts](https://github.com/YCloudYUSA/yusaopeny_activity_finder#trusted-redirect-host-patterns) to be redirected, but **if no trusted host is configured then any host was previously allowed through**. 

This could provide an attack vector where a malicious site could use the "trusted" YMCA domain to redirect users to an untrusted site, like `exampleymca.org/af/register-redirect/1234?url=https://examplephishers.net`.<br>

## How bad is it?

Using the [Drupal Security Risk Calculator](https://security.drupal.org/riskcalc) this risk has been assessed as 12/25 (Moderately Critical): `AC:Basic/A:None/CI:None/II:None/E:Exploit/TD:Default`.

Here's what that means:

* Access complexity: It is trivial for an attacker to leverage the vulnerability.
* Authentication: No authentication is needed for an exploit to be successful.
* Confidentiality Impact: The vulnerability does not cause non-public data to become accessible.
* Integrity Impact: The vulnerability can not allow system data to be compromised.
* Zero-day Impact: An documented exploit does exist in the wild.
* Target Distribution: Default module configurations are exploitable, but a config change can disable the exploit.

## What do we do?

There are two mitigations, available to you to use immediately:

1. If your site is actively using Activity Finder, you should immediately ensure your site has the `activity_finder_trusted_redirect_host_patterns`configured in `settings.php` as per [the documentation](https://github.com/YCloudYUSA/yusaopeny_activity_finder#trusted-redirect-host-patterns). After deploying this change and clearing caches, your site will be secure. **If you do not make this change**, your Activity Finder links may stop redirecting on your next code update.
2. If your site is not actively using Activity Finder, update to the [latest release of Activity Finder](https://github.com/YCloudYUSA/yusaopeny_activity_finder/releases/tag/4.1.15) or [include this patch](https://github.com/YCloudYUSA/yusaopeny_activity_finder/pull/9) to enforce the security of your site, as the Activity Finder code could still be active even though it's not being used.