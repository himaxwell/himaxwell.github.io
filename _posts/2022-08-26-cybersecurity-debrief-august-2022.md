---
layout: post
title: 'This Month in Cybersecurity: August 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at August 2022's top cybersecurity stories.
---

##  Major News Stories
#### Double Check that Github URL
[BleepingComputer reports](https://www.bleepingcomputer.com/news/security/35-000-code-repos-not-hacked-but-clones-flood-github-to-serve-malware/) that some 35,000 Github repositories were forked and their clones modified to include malware. No actual compromises took place; rather, "The thousands of backdoored projects are copies (forks or clones) of legitimate projects purportedly made by threat actors to push malware." This is a clever attack and a good reminder to always make sure you're using the repo that you think you're using!

#### Atlassian Confluence aka. The Sitting Duck
The venerable Confluence web-based wiki turns 18 this year. Even thought that makes it a legal adult in the U.S., apparently it's not quite ready for life without significant adult supervision as attackers have discovered a devastating vulnerability in all Confluence wikis that either currently have or at one point in the past installed the "Questions For Confluence" (QFC) app.

The issue stems from the fact that, once installed, the QFC app creates a user with a hard-coded password, one that allows access to all nonrestricted pages in the wiki. Atlassian, the maker of Confluence, notes that uninstalling the QFC app doesn't remediate the issue, most likely since the user and its hard-coded password remain in the database. Atlassian has patched the actively-exploited bug and urges admins to update their Confluence instances quickly.

#### Vulnerabilities Found in the Emergency Broadcast Messaging System
“We recently became aware of certain vulnerabilities in EAS encoder/decoder devices that, if not updated to most recent software versions, could allow an actor to issue EAS alerts over the host infrastructure (TV, radio, cable network).” ([Source](https://content.govdelivery.com/accounts/USDHSFEMA/bulletins/3263326))

#### Slack Patches Vulnerability that Leaked Hashed Passwords for a Small Subset of Users
“On 4 August 2022, we notified approximately 0.5% of Slack users that we had reset their passwords in response to a bug that occurred when users created or revoked a shared invitation link for their workspace. When a user performed either of these actions, Slack transmitted a hashed version of their password to other workspace members. This hashed password was not visible to any Slack clients; discovering it required actively monitoring encrypted network traffic coming from Slack’s servers.” ([Source](https://slack.com/intl/en-in/blog/news/notice-about-slack-password-resets))

#### Zoom as a MacOS Attack Vector
A serious [flaw in Zoom for MacOS](https://www.theverge.com/2022/8/12/23303411/zoom-defcon-root-access-privilege-escalation-hack-patrick-wardle) was presented at Defcon 2022. Sector 7 has [a great write-up](https://sector7.computest.nl/post/2022-08-process-injection-breaking-all-macos-security-layers-with-a-single-vulnerability/) on how the vulnerability works, but in short researchers used it to bypass multiple levels of protection to gain root access on MacOS. Zoom attempted to patch the flaw in version 5.11.5; however, that fix was insufficient and was bypassed several days after release, causing Zoom to issue version 5.11.6.

#### Welcoming the "Open Cybersecurity Schema Framework"
A number of heavy-hitters in the tech space, including AWS, Cloudflare, and IBM Security, have come together to create The Open Cybersecurity Schema Framework (OCSF): [https://github.com/ocsf/](https://github.com/ocsf/). The goal of the framework is to provide a standard set of categories and names around various cybersecurity-related topics, events, etc. The ultimate end goal is that organization A and organization B can reference for example a "Network Activity Event" and both be referring to the same concept as outlined in the OCSF.

## Other Software with Critical Patches Available
* [Firefox version 104 addressed several high-severity CVE's](https://www.mozilla.org/en-US/security/advisories/mfsa2022-33/).
* Microsoft August 2022 Patch Tuesday notes: [https://isc.sans.edu/diary/Microsoft+August+2022+Patch+Tuesday/28924](https://isc.sans.edu/diary/Microsoft+August+2022+Patch+Tuesday/28924)
* Adobe Security Patches for August 2022: [https://helpx.adobe.com/security/security-bulletin.html](https://helpx.adobe.com/security/security-bulletin.html)
* [DrayTek Vigor routers have an unauthenticated remote code execution vulnerability that was recently patched.](https://www.trellix.com/en-us/about/newsroom/stories/threat-labs/rce-in-dratyek-routers.html)
* [Jenkins recently patched a large number of CVEs](https://www.jenkins.io/security/advisory/2022-07-27/).

## Deep Dives
A few interesting deep-dive reads from the month:
* [Hijacking email with Cloudflare Email Routing](https://albertpedersen.com/blog/hijacking-email-with-cloudflare-email-routing/)
* [Manjusaka: A Chinese sibling of Sliver and Cobalt Strike](https://blog.talosintelligence.com/2022/08/manjusaka-offensive-framework.html)
* [Janet Jackson had the power to crash laptop computers](https://devblogs.microsoft.com/oldnewthing/20220816-00/?p=106994)
* BONUS: Not cybersecurity-focused per se, but a great read nonetheless: [The Munger Operating System: How to Live a Life That Really Works](https://fs.blog/munger-operating-system/)

## Learning -- `CVE-2007-5379`
First recorded on October 11, 2007 and earning itself a CVE score of 5.0 out of 10, the description for `CVE-2007-5379` reads, "Rails before 1.2.4, as used for Ruby on Rails, allows remote attackers and ActiveResource servers to determine the existence of arbitrary files and read arbitrary XML files via the Hash.from_xml (Hash#from_xml) method, which uses XmlSimple (XML::Simple) unsafely, as demonstrated by reading passwords from the Pidgin (Gaim) .purple/accounts.xml file."

Pidgin is an open-source IM client, formerly known as "Gaim." [1] Apparently, it stored/stores passwords in a `.purple/accounts.xml` file. It appears that researchers read from this file as a sort of proof-of-concept for this exploit since it allowed for the reading of arbitrary XML files.

The commit that fixed this vulnerability is available [here](https://github.com/rails/rails/commit/b29caa54e61cccfc330d47bbe5839970c94bb36e) with the fun comment, "Same as xml_in but doesn't try to smartly shoot itself in the foot" over a new `xml_in_string` method.

[1] [https://en.wikipedia.org/wiki/Pidgin_(software)](https://en.wikipedia.org/wiki/Pidgin_(software))  

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)
* [https://thehackernews.com/2022/07/cisa-warns-of-atlassian-confluence-hard.html](https://thehackernews.com/2022/07/cisa-warns-of-atlassian-confluence-hard.html)
* [https://www.darkreading.com/cloud/patch-now-atlassian-confluence-bug-active-exploit](https://www.darkreading.com/cloud/patch-now-atlassian-confluence-bug-active-exploit)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏾‍💻 🌐 👨‍💻
