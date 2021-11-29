In order to protect Open Y customers, we added anti-spam protection, based on Captcha, Google reCaptcha, out of the box in Open Y core
You can check [the tutorial for how to install and configure reCaptcha on your site.](https://www.youtube.com/watch?v=nHo2uL-bPyM)

In the majority of cases having the above configuration in place will protect you from 99% of the spam, unless there is a human entered spam that has no protection. To overcome some human-based spam you should use blacklist logic for blocking email domains, used in spam messages.
For that, you can use https://dgo.to/protected_submissions module which allows you to harden all submissions on a site with a list of stop words as well as per language settings.

## Virtual Y use case

In order to overcome caching issues, Virtual Y uses a simple_recaptcha module which could be used in the same cases.

Some time ago we have faced the issue when “Captcha” + “reCAPTCHA” have been working wrong on some projects, we are supporting: every time the challenge was solved – the form wasn’t validated on a submit for some reason.
There was some issue on drupal.org regarding such issues (the last blocker was https://www.drupal.org/project/captcha/issues/3089263 ), and a bunch of patches, that should resolve the issues, so that times we’ve applied the patches and sometimes that helped, sometimes – not.
At some point, the “Simple reCaptcha” module was used on a first project, and it had no issues with the challenges' wrong checks – so we’ve started to replace the “Captcha” + “reCAPTCHA” modules bunch with the “Simple reCaptcha”.

As for the VY, we’ve again faced the issue that the challenge solved hasn’t passed the validation, even being on the last version of the reCAPTCHA module, which has already merged in the fix for the issue.