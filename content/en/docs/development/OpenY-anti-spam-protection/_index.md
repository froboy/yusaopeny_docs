---
title: anti spam protection
aliases:
  - /docs/wiki/openy-anti-spam-protection/
---

In order to protect YMCA Website Services customers, we have added anti-spam protection based on CAPTCHA and Google reCAPTCHA out of the box in YMCA Website Services core

You can check [the tutorial for how to install and configure reCaptcha on your site](https://www.youtube.com/watch?v=sx36hoDj4Wc).

In the majority of cases having the above configuration in place will protect you from 99% of spam, unless there is human-entered spam that has no protection. To overcome some human-based spam you should use blacklist logic for blocking email domains, used in spam messages.

For that, you can use [the Protected Submissions module](https://www.drupal.org/project/protected_submissions) module, which allows you to harden all submissions on a site with a list of stop words as well as per-language settings.

## Virtual Y use case

In order to overcome caching issues, Virtual Y uses the [simple_recaptcha](https://www.drupal.org/project/simple_recaptcha) module which could be used in similar cases.

The CAPTCHA + reCAPTCHA module solution has presented some reliability issues. The most recent [discussion and fix from drupal.org](https://www.drupal.org/project/captcha/issues/3089263) has also not reliably resolved issues for some clients.

At some point, the “Simple reCaptcha” module was used on a project and had no issues, so we’ve started to replace the “CAPTCHA” + “reCAPTCHA” modules with “Simple reCAPTCHA”.
