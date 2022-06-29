---
layout: post
title: 'This Week in Cybersecurity: June 19-25, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---

##  Major News Stories
* Happy that Microsoft's officially ending support for Internet Explorer this month means your Windows PC has one less attack surface to worry about? Maybe hold the champagne - [remnants of the venerable (vulnerable?) web browser remain part of the core Windows OS](https://www.darkreading.com/vulnerabilities-threats/internet-explorer-will-likely-remain-an-attacker-target-for-some-time) and, "Will likely remain an attack target for some time."
* This week, SANS released an experimental API for determining the age of a domain name, helpful since the longer a domain has been around the less likely it is to be malicious. You can read more about the API [here](https://isc.sans.edu/forums/diary/Experimental+New+Domain+Domain+Age+API/28770/).
* On Tuesday, Cloudflare had an outage that briefly [took down a large number of popular websites](https://techcrunch.com/2022/06/20/cloudflare-outage-knocks-popular-services-offline/). On Wednesday, they released a [detailed write-up](https://blog.cloudflare.com/cloudflare-outage-on-june-21-2022/). TL;DR - "This outage was caused by a change that was part of a long-running project to increase resilience in our busiest locations. A change to the network configuration in those locations caused an outage...This was our error and not the result of an attack or malicious activity."
* A few interesting deep-dive reads from the week:
  * [Proofpoint Discovers Potentially Dangerous Microsoft Office 365 Functionality that can Ransom Files Stored on SharePoint and OneDrive](https://www.proofpoint.com/us/blog/cloud-security/proofpoint-discovers-potentially-dangerous-microsoft-office-365-functionality)

## Other Software with Critical Patches Available
* Nothing major this week.

## Learning -- `CVE-2006-4112`
[A few weeks back, we looked at `CVE-2006-4111`]({% link _posts/2022-05-13-cybersecurity-debrief-2022-05-14.md %}), the very first Ruby on Rails CVE. This week, we're continuing our journey through Rails' CVE history and taking a look at the second CVE to affect the framework - `CVE-2006-4112` [1].

Published the same day as `CVE-2006-4111` (the first Rails CVE) and tying `4111`'s CVSS score of 7.5/10, `CVE-2006-4112` was classified with the vulnerability types of "denial of service" and "code execution". [The blog post from the Rails team regarding the vulnerability](https://rubyonrails.org/2006/8/9/rails-1-1-5-mandatory-security-patch-and-other-tidbits) is quite interesting when considering the evolution of the Rails team's approach to security vulnerabilities.

For example, the current industry best practice for open source projects like Rails is to be forthcoming regarding the details of a security vulnerability. However, in the above-mentioned blog post, DHH declines to discuss any specifics of the security issue, stating, "The issue is in fact of such a criticality that we’re not going to dig into the specifics. No need to arm would-be assalients [sic]." This "security by obscurity" approach is considered counterproductive as it prevents white hats from validating a fix (interestingly, this CVE had a 1.1.5 patch that was released and then withdrawn due to multiple issues) and doesn't stop black hats since a simple diff between versions is enough for would-be attackers to begin crafting an exploit.

And in fact, that approach was quickly taken, albeit (and thankfully) by the white-hat Evan Weaver, who posted, ["anatomy of an attack against 1.1.4"](https://blog.evanweaver.com/2006/08/12/anatomy-of-an-attack-against-1-1-4/) to his blog. In this post, Evan uncovers the vulnerable code by starting with a fresh Rails app and diffing the changes between 1.1.4 and 1.1.5. The post is definitely worth a read and does an excellent job of breaking down two very serious vulnerabilities that were fixed in Rails 1.1.6:
1. Being able to request arbitrary files (i.e., in a Rails app's `lib/` and `db/` folders), causing DOS and database corruption. And,
2. Mechanisms for running arbitrary code via Rail's `$LOAD_PATH` (different from `CVE-2006-4111`).

[1] [https://www.cvedetails.com/cve-details.php?t=1&cve_id=CVE-2006-4112](https://www.cvedetails.com/cve-details.php?t=1&cve_id=CVE-2006-4112)  

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://github.com/presidentbeef/rails-security-history/blob/master/vulnerabilities.md#cve-2006-4111cve-2006-4112](https://github.com/presidentbeef/rails-security-history/blob/master/vulnerabilities.md#cve-2006-4111cve-2006-4112)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏿‍💻 🌐 👨🏽‍💻
