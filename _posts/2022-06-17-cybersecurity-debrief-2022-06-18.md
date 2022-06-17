---
layout: post
title: 'This Week in Cybersecurity: June 12-18, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---

##  Major News Stories
* This week, Heroku released the results of its investigation into the events surrounding its April 2022 data breach. The full blog post is available [here](https://blog.heroku.com/april-2022-incident-review), but if you're hoping for a detailed discussion of the attack's source, prepare to be disappointed as Heroku states, "[We] have been unable to definitively confirm the third-party integration that was the source of the attack."
* This week was patch Tuesday. In addition to a number of CVEs rated "critical," Microsoft has fixed the much-publicized Follina vulnerability (for a refresher on Follina, see the [June 4, 2022 cybersecurity debrief]({% link _posts/2022-06-03-cybersecurity-debrief-2022-06-04.md %})).
* This week also saw several new CPU attacks unveiled.
  * Researchers have discovered a new CPU side-channel attack called HertzBleed. The attack leverages the frequency adjustments that CPUs make, and it looks like cryptographic operations are thought to be the most-vulnerable to this attack. The vulnerability has a dedicated website here: [https://www.hertzbleed.com](https://www.hertzbleed.com/).
  * [PACMAN](https://pacmanattack.com) is a novel hardware attack on Apple's M1 chip. The attack, "Takes an existing software bug (memory read/write) and turns it into a more serious exploitation primitive (a pointer authentication bypass), which may lead to arbitrary code execution."
* A quick reminder for developers - make sure you're spelling your dependencies correctly!
  * The PyPI package `requests` is a legitimate library used for making HTTP requests; however, the `request` package (no _s_) contains malware.
  * This week, [BleepingComputer reported on several projects](https://www.bleepingcomputer.com/news/security/pypi-package-keep-mistakenly-included-a-password-stealer/) that were using the misspelled, malware-infested package.
* A few interesting deep-dive reads from the week:
  * [New ultra-stealthy Linux backdoor isn’t your everyday malware discovery](https://arstechnica.com/information-technology/2022/06/novel-techniques-in-never-before-seen-linux-backdoor-make-it-ultra-stealthy/)

## Other Software with Critical Patches Available
* [Adobe released a large slate of updates for its products this week](https://helpx.adobe.com/security/security-bulletin.html).

## Learning -- Defense In Depth: Quick Tip
We discussed some practical defense-in-depth strategies [a few weeks ago]({% link _posts/2022-06-03-cybersecurity-debrief-2022-06-04.md %}), but since this week was so news-heavy, I wanted to throw out another quick tip for protecting yourself online.

It's no secret that the majority of websites these days deploy tracking/targeting technologies of various sorts, some of which can track users across websites. Thus, it's a good practice to try to isolate websites from each other. One of the easiest ways to do so is to use the [Firefox web browser](https://getfirefox.com), which [just launched Total Cookie Protection for all desktop users](https://blog.mozilla.org/en/products/firefox/firefox-rolls-out-total-cookie-protection-by-default-to-all-users-worldwide/). Firefox also has several extensions that you can use to further isolate websites from each other:
* [Multi-Account Containers (Firefox extension)](https://support.mozilla.org/en-US/kb/containers): "Lets you keep parts of your online life separated into color-coded tabs that preserve your privacy. Cookies are separated by container, allowing you to use the web with multiple identities or accounts simultaneously, as well as integrating Mozilla VPN for an extra layer of privacy."
* [Facebook Container (Firefox extension)](https://addons.mozilla.org/en-US/firefox/addon/facebook-container/): Prevent Facebook from tracking you around the web. The Facebook Container extension for Firefox helps you take control and isolate your web activity from Facebook.

If you don't want to step away from Google Chrome entirely but still want to improve your online privacy, some other good options include:
* Using the [uBlock Origin](https://ublockorigin.com) and/or [Privacy Badger](https://privacybadger.org) extensions to limit ad tracking.
* Using a privacy-focused fork of Google Chrome like the [Vivaldi](https://vivaldi.com) or [Brave](https://brave.com) web browsers.

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏿‍💻 🌐 👨🏽‍💻
