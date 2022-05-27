---
layout: post
title: 'This Week in Cybersecurity: May 15-21, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---

##  Major News Stories
* According to a a recent post from NCC Group, Tesla automobiles are vulnerable to Bluetooth relay attacks. The [technical advisory](https://research.nccgroup.com/2022/05/15/technical-advisory-tesla-ble-phone-as-a-key-passive-entry-vulnerable-to-relay-attacks/) states, "An attacker within Bluetooth signal range of a mobile device configured for Phone-as-a-Key use can conduct a relay attack to unlock and operate a vehicle despite the authorized mobile device being out of range of the vehicle." The group recommends using the "PIN to Drive" feature as a way to mitigate this attack.
* The [April 20222 Heroku breach](https://status.heroku.com/incidents/2413) may be a bit worse than initially thought.
  * This week, Heroku customers received the following via email:
  > As reported on status.heroku.com, on April 7, 2022, a threat actor obtained access to a Heroku database and downloaded stored customer GitHub integration OAuth tokens. On that same day, the threat actor downloaded data from another database that stores pipeline-level config vars for Review Apps and Heroku CI. This was identified on May 16, 2022, after further forensic investigation. We have no evidence of any unauthorized access to Heroku systems since April 14, 2022.
  >
  > As a result, any secrets you set in Review Apps and Heroku CI config vars may have been compromised and should be rotated. In addition, any Heroku tokens stored in these pipeline config vars would potentially have allowed access to your Heroku account between April 7, 2022 and May 5, 2022, when your passwords were reset, invalidating all Heroku tokens as a result.

  * The email does go on to note that, "These pipeline-level config vars are different from standard app config vars. App config vars were not stored in this database and we have no evidence to suggest app config vars were compromised."  

* The US Cybersecurity and Infrastructure Security Agency (CISA) has warned not to install the May 2022 Windows updates on domain controllers. Apparently the fix for CVE-2022-26925 has left some organizations' users unable to login. The issue seems to be with the patch itself, [prompting one commentator to note](https://www.grc.com/sn/SN-871-Notes.pdf), "We're back to that disheartening story of Microsoft patching to stop a proof of concept from functioning, while leaving the underlying problem unresolved."
* A few interesting deep-dive reads from the week:
  * ["Zero-Days" Without Incident - Compromising Angular via Expired npm Publisher Email Domains](https://thehackerblog.com/zero-days-without-incident-compromising-angular-via-expired-npm-publisher-email-domains-7kZplW4x/)

## Other Software with Critical Patches Available
* On Monday, Apple released updates for "tvOS, Xcode, macOS (Bug Sur, Monterey, and Catalina), iOS, iPadOS and WatchOS. In addition to new features, the updates patch a total of 86 vulnerabilities." Sans has a nice breakdown of the fixes [here](https://isc.sans.edu/diary/rss/28654s).
* [Sonicwall](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2022-0009) and [Zonealarm](https://www.zonealarm.com/software/extreme-security/release-history) patched several nasty bugs in their security products.

## Learning -- What is a zero-day?
When reading the popular and/or tech press, one often hears of the latest zero-day (aka. 0-day) exploit in this or that popular product or software. But what exactly is a 0-day? And how can you tell if a security vulnerability is in fact a 0-day?

One of the issues with the term 0-day is that it sounds really cool, so it's often slapped on pretty much any vulnerability that comes along. However, the original concept of a 0-day is that it is, "an unknown exploit in the wild that exposes a vulnerability in software or hardware and can create complicated problems well before anyone realizes something is wrong." [1] Thus, in order for a vulnerability to be considered a 0-day, it must be unknown prior to someone discovering its actual use by an attacker. If a security researcher discovers and responsibly discloses a vulnerability, it's not a 0-day.

0-days are an important facet of cybersecurity since they represent things that bad actors know and are using in attacks that good actors aren't aware of and thus can't scan for or protect against. 0-days are secret weapons that no one knows about until they claim one or more victims: "Once a patch is written and used, the exploit is no longer called a zero-day exploit. These attacks are rarely discovered right away. In fact, it often takes not just days but months and sometimes years before a developer learns of the vulnerability that led to an attack." [1]

Thus, the importance of the concept of "defense in depth" - attacks can't always be prevented, so they must be monitored for and controls put in place such that their impact is limited. We'll talk more about defense-in-depth next time.

[1] [https://www.fireeye.com/current-threats/what-is-a-zero-day-exploit.html](https://www.fireeye.com/current-threats/what-is-a-zero-day-exploit.html)  

## Sources & Resources
The following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now/episodes/871?autostart=false](https://twit.tv/shows/security-now/episodes/871?autostart=false)
* [https://www.grc.com/sn/SN-871-Notes.pdf](https://www.grc.com/sn/SN-871-Notes.pdf)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏾‍💻 🌐 👨🏼‍💻
