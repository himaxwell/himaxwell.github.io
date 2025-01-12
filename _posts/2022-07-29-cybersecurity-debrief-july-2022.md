---
layout: post
title: 'This Month in Cybersecurity: July 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at July 2022's top cybersecurity stories.
---

##  Major News Stories
#### MS Office Macros: There and Back Again
In February of this year, Microsoft caused joy and celebration throughout the cybersecurity industry when [they announced](https://techcommunity.microsoft.com/t5/microsoft-365-blog/helping-users-stay-safe-blocking-internet-macros-by-default-in/ba-p/3071805), "We’re introducing a default change for five Office apps that run macros: VBA macros obtained from the internet will now be blocked by default." As a little background, macros are essentially scripts that can add functionality to MS Office documents that, while useful, are also a notorious threat vector, often delivering malware, ransomeware, and other attacks.

However, it appears that they are also widely used, which on July 8, 2022 prompted Microsoft to roll back the change with the note, "Following user feedback, we have rolled back this change temporarily while we make some additional changes to enhance usability. This is a temporary change, and we are fully committed to making the default change for all users."

Twelve days later on July 20, Microsoft did just that and resumed rollout of the change, [noting](https://techcommunity.microsoft.com/t5/microsoft-365-blog/helping-users-stay-safe-blocking-internet-macros-by-default-in/ba-p/3071805), "We’re resuming the rollout of this change in Current Channel. Based on our review of customer feedback, we’ve made updates to both our end user and our IT admin documentation to make clearer what options you have for different scenarios. For example, what to do if you have files on SharePoint or files on a network share." Fingers crossed the change sticks this time!

#### July 2022 Patch Tuesday
In this month's patch Tuesday on July 12, Microsoft released updates for 86 vulnerabilities, 4 of which were rated "critical."

#### Spectre's Spectre: Retbleed
[Retbleed](https://arstechnica.com/information-technology/2022/07/intel-and-amd-cpus-vulnerable-to-a-new-speculative-execution-attack/?comments=1) is a new variation of the Spectre attack that targets the "speculative execution" feature of modern CPUs. (For an explanation of what Spectre is and how it works, check out the "Learning" section below.) Previously, "Retpolines" were used as a way to mitigate Spectre: "A retpoline works by replacing indirect jumps and calls [susceptible to speculative attacks] with returns, which many researchers presumed weren’t susceptible." The Retbleed attack undermines this mitigation: "Retbleed shows that return instructions unfortunately leak under certain conditions similar to indirect branches. These conditions are unfortunately common on both Intel (Skylake and Skylake-based) and AMD (Zen, Zen+ and Zen2) platforms. This means that retpoline was unfortunately an inadequate mitigation to begin with."

Linux is currently the only major OS that has been shown to be vulnerable to this attack. Mitigations are forthcoming; however, they contain a major performance hit: "Both Intel and AMD advised customers to adopt new mitigations that the researchers said will add as much as 28 percent more overhead to operations."

#### CosmicStrand: Hide Your Kids, Hide Your UEFI
Think wiping your drive and re-installing your OS is enough to get rid of a malware infection? Think again. Researchers from Kaspersky have announced the discovery of [CosmicStrand](https://arstechnica.com/information-technology/2022/07/researchers-unpack-unkillable-uefi-rootkit-that-survives-os-reinstalls/), "A sophisticated UEFI rootkit."

Kaspersky [notes](https://securelist.com/cosmicstrand-uefi-firmware-rootkit/106973/) that, "Rootkits are malware implants which burrow themselves in the deepest corners of the operating system. Although on paper they may seem attractive to attackers, creating them poses significant technical challenges and the slightest programming error has the potential to completely crash the victim machine." Kaspersky continues, "One of the main draws towards malware nested in such low levels of the operating system is that it is extremely difficult to detect and, in the case of firmware rootkits, will ensure a computer remains in an infected state even if the operating system is reinstalled or the user replaces the machine’s hard drive entirely."

CosmicStrand is unique among rootkits in that, "This UEFI implant seems to have been used in the wild since the end of 2016 – long before UEFI attacks started being publicly described. This discovery begs a final question: if this is what the attackers were using back then, what are they using today?"

#### Hijacked: Apple IP Space Temporarily Directs Users to Russia
For about 12 hours on July 26-27, Rostelecom (Russia's largest digital services provider) hijacked a range of IP addresses belonging to Apple. "The effect was that Internet users in parts of the Internet trying to connect to Apple’s services may have been redirected to the Rostelecom network." ([Source](https://www.manrs.org/2022/07/for-12-hours-was-part-of-apple-engineerings-network-hijacked-by-russias-rostelecom/)) Apple has since addressed the issue on its side and Rostelecom has stopped advertising itself as a route for these IPs. No word yet on whether or not this was a malicious action or simply a mistake on Rostelecom's part.

## Other Software with Critical Patches Available
* Apple patched "all the things" the week of July 17-23. One of the issues is [rated "critical" by SANS](https://isc.sans.edu/diary/Apple+Patches+Everything+Day/28862) and affects pretty much all iDevices, so update ASAP.
* Adobe released a [large slew of updates mid-month](https://helpx.adobe.com/security/security-bulletin.html), including updates for Acrobat and Photoshop.
* [Oracle patched a large number of its products around the 20th](https://www.oracle.com/security-alerts/cpujul2022.html). Among the many issues fixed was a CVE with a perfect 10/10 CVSS score.
* [Cisco released a number of security updates for its products](https://tools.cisco.com/security/center/publicationListing.x?).

## Deep Dives
A few interesting deep-dive reads from the month:
* [Uncovering a macOS App Sandbox escape vulnerability: A deep dive into CVE-2022-26706](https://www.microsoft.com/security/blog/2022/07/13/uncovering-a-macos-app-sandbox-escape-vulnerability-a-deep-dive-into-cve-2022-26706/)
* [IcedID Infection Leads to Dark VNC Activity and Cobalt Strike Malware](https://isc.sans.edu/diary//28884)

## Learning -- Spectre
Spectre is, "A subset of security vulnerabilities within the class of vulnerabilities known as microarchitectural timing side-channel attacks." [1] It was first publicly announced in January 2018 alongside the related Meltdown vulnerabilities. Since its initial discovery, many variations of the attack have been discovered, most-recently Retbleed as discussed earlier.

In short, the Spectre attack takes advantage of the fact that, when faced with one or more branching code paths, many processors speculatively execute all possible paths in order to boost performance, ignoring any unused paths which nonetheless remain in the CPU cache. It is these in-cache speculative executions that can be compromised via timing attacks to leak secrets. [This ~4-minute YouTube video](https://www.youtube.com/watch?v=q3-xCvzBjGs) does an excellent job explaining the mechanics of actually exploiting Spectre via a timing attack.

While the initial Spectre vulnerability has long been patched/mitigated, this vulnerability's name has proven quite prescient as its ghost has constantly defied death and resurrected itself in new, often more-terrifying forms. As the recent Retbleed vulnerability proves, it will likely continue to haunt us for many years to come.

[1] [https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)](https://en.wikipedia.org/wiki/Spectre_(security_vulnerability))  

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://events19.linuxfoundation.cn/wp-content/uploads/2017/11/Understanding-Spectre-v2-and-How-the-Vulnerability-Impact-the-Cloud-Security_Gavin-Guo.pdf](https://events19.linuxfoundation.cn/wp-content/uploads/2017/11/Understanding-Spectre-v2-and-How-the-Vulnerability-Impact-the-Cloud-Security_Gavin-Guo.pdf)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏽‍💻 🌐 👨🏻‍💻
