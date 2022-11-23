---
layout: post
title: 'This Month in Cybersecurity: November 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at November 2022's top cybersecurity stories.
---

##  Major News Stories
#### Critical OpenSSL 3.0 Update Released
On November 1, OpenSSL released version 3.0.7, which patches CVE-2022-3786 and CVE-2022-3602, vulnerabilities which only affect the OpenSSL 3.0.x series.

This release is notable since many were concerned about another Heartbleed-like vulnerability, which many of you may recall was discovered in 2014 and [when exploited led](https://heartbleed.com/), "To the leak of memory contents from the server to the client and from the client to the server." Heartbleed lives in infamy as a relatively easy-to-exploit bug with broad exposure and high impact.

Thankfully, these vulnerabilities have proven to be much less potent than Heartbleed. For those interested, SANS has a write-up [here](https://isc.sans.edu/diary/Critical+OpenSSL+30+Update+Released+Patches+CVE20223786+CVE20223602/29208), while DataDog has very in-depth article [here](https://securitylabs.datadoghq.com/articles/openssl-november-1-vulnerabilities/).

#### Friendly Fire: MacOS Ventura Bug Breaks Third-Party Security Tools
Turns out, your anti-malware software may not work if you upgraded to the latest operating system from Apple. Wired [reports](https://www.wired.com/story/apple-macos-ventura-bug-security-tools/), "In the process of patching a vulnerability in the 11th Ventura developer beta, released on October 11, Apple accidentally introduced a flaw that cuts off third-party security products from the access they need to do their scans. And while there is a workaround to grant the permission, those who upgrade their Macs to Ventura may not realize that anything is amiss or have the information needed to fix the problem. "

Apple says a fix is on the way, and there are [workarounds available in the meantime](https://www.macobserver.com/tips/deep-dive/bug-in-macos-ventura-may-have-silently-broken-your-malware-protection-heres-how-to-fix-it/).

#### Interesting Bugs Abound
November also brought several interesting bugs in the flagship mobile operating systems.

For Android, a simple [lock screen bypass](https://techcrunch.com/2022/11/14/android-lock-screen-bypass-google-pixel/) netted a security researcher $70,000. "Hungary-based researcher David Schütz said the bug was remarkably simple to exploit but took Google about five months to fix."

For iOS, researchers discovered [`WeightBufs`](https://github.com/0x36/weightBufs/), "A kernel r/w exploit for all Apple devices with Neural Engine support." A nice presentation with a deep-dive on the vulnerability is available [here](https://github.com/0x36/weightBufs/blob/main/attacking_ane_poc2022.pdf).

## Other Software with Critical Patches Available
* [Google Chrome 0-Day Patch](https://chromereleases.googleblog.com/2022/10/stable-channel-update-for-desktop_27.html)
* [Microsoft has Finally Patched that Troublesome Exchange Server Vulnerability](https://msrc-blog.microsoft.com/2022/09/29/customer-guidance-for-reported-zero-day-vulnerabilities-in-microsoft-exchange-server/)
* [Microsoft’s November 2022 Patch Tuesday Patched 68 Vulnerabilities (10 critical, 1 previously disclosed, and 4 actively-exploited).](https://isc.sans.edu/diary/Microsoft%20November%202022%20Patch%20Tuesday/29230)
* [Apple Released Security Updates for Most of Its Software This month](https://support.apple.com/en-us/HT201222)

## Deep Dives
A few interesting deep-dive reads from the month:
* [Disneyland Malware Team: It’s a Puny World After All](https://krebsonsecurity.com/2022/11/disneyland-malware-team-its-a-puny-world-after-all/)
* [New Extortion Scam Threatens To Damage Sites’ Reputation, Leak Data](https://www.bleepingcomputer.com/news/security/new-extortion-scam-threatens-to-damage-sites-reputation-leak-data/)

## Learning -- `CVE-2007-6077`
First disclosed on November 21 2007, and earning itself a CVSS score of 6.8/10, `CVE-2007-6077` is one of those "sometimes you don't get it right the first time" type of fixes:

> The session fixation protection mechanism in cgi_process.rb in Rails 1.2.4, as used in Ruby on Rails, removes the :cookie_only attribute from the DEFAULT_SESSION_OPTIONS constant, which effectively causes cookie_only to be applied only to the first instantiation of CgiRequest, which allows remote attackers to conduct session fixation attacks.
>
> **NOTE: this is due to an incomplete fix for CVE-2007-5380.**

For a full breakdown of `CVE-2007-5380` (which should give more context to this CVE and session fixation in general), see the [October 2022 Cyberecurity Debrief]({% link _posts/2022-10-27-cybersecurity-debrief-october-2022.md %}).

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏿‍💻 🌐 👨‍💻
