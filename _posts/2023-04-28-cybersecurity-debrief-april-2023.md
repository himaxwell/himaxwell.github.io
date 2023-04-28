---
layout: post
title: 'This Month in Cybersecurity: April 2023'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at April 2023's top cybersecurity stories.
---

##  Major News Stories
### Ouch! PaperCut Vulnerability a 9.8/10
There have been some great exploit names over the years (Heartbleed and ReVoLTE come to mind), and while PaperCut would be another great one, it's actually the name of a company that creates software for managing printers.

Back in March, the company [patched a CVE with a 9.8/10 severity](https://arstechnica.com/information-technology/2023/04/exploit-released-for-9-8-severity-papercut-flaw-already-under-attack/):

> The vulnerability, tracked as CVE-2023–27350, carries a severity rating of 9.8 out of a possible 10. It allows an unauthenticated attacker to remotely execute malicious code without needing to log in or provide a password. A related vulnerability, tracked as CVE-2023–27351 with a severity rating of 8.2, allows unauthenticated attackers to extract usernames, full names, email addresses, and other potentially sensitive data from unpatched servers.

Apparently, not many PaperCut users installed the update, and active-exploitation kicked off in earnest on April 19, with the above ARS article noting there are around 1,700 PaperCut instances publicly exposed on the internet.

### SANS Reports on The Five Most Dangerous New Attack Techniques
> Each year at RSA Conference, SANS provides the authoritative briefing on the most dangerous new attack techniques in use today, what's coming next, and what organizations can do to prepare. This session gives organizations a chance to prioritize upcoming attack vectors and to get ahead of them.
>
> [source](https://www.rsaconference.com/usa/agenda/session/The%20Five%20Most%20Dangerous%20New%20Attack%20Techniques)

You can read the full report [here](https://www.csoonline.com/article/3694892/5-most-dangerous-new-attack-techniques.html), but the top-five attacks identified for 2023 were:
1. Adversarial AI
1. ChatGPT-powered social engineering
1. Third-party developer attacks
1. SEO
1. Paid advertising attacks

It's interesting that all these attacks have one theme in common: Exploiting humans as the weak link when it comes to cybersecurity.

### 3CX Breach Update
3CX is a VoIP/PBX provider that was [recently compromised](https://arstechnica.com/information-technology/2023/03/3cx-knew-its-app-was-flagged-as-malicious-but-took-no-action-for-7-days/):

> A threat group tied to the North Korean government compromised the 3CX software build system and used the control to push Trojanized versions of the company’s DesktopApp programs for Windows and macOS. The malware causes infected machines to beacon to actor-controlled servers and, depending on unknown criteria, the deployment of second-stage payloads to specific targets. In a few cases, the attackers carried out “hands-on-keyboard activity” on infected machines, meaning the attackers manually ran commands on them.

The attack [appears to have been quite sophisticated](https://securelist.com/gopuram-backdoor-deployed-through-3cx-supply-chain-attack/109344/):

> * The infection is spread via 3CXDesktopApp MSI installers. An installer for macOS has also been trojanized.
> * The malicious installation package contains an infected dll library that decrypts a shellcode from the d3dcompiler_47.dll library’s overlay and executes it.
> * The decrypted payload extracts C2 server URLs from icons stored in a GitHub repository (the repository is removed).
> * The payload connects to one of the C2 servers, downloads an infostealer and starts it.
> * The infostealer collects system information and browser history, then sends it to the C2 server.

To their credit, 3CX has been very vocal throughout the entire remediation process, posting multiple updates to their blog, including:
- [Security Update Tuesday 11 April 2023 - Interim Assessment Concluded](https://www.3cx.com/blog/news/mandiant-initial-results/)
- [Security Update Thursday 20 April 2023 – Initial Intrusion Vector Found](https://www.3cx.com/blog/news/mandiant-security-update2/)
- [Actions not words - Our 7 Step Security Action Plan!](https://www.3cx.com/blog/news/security-action-plan/)

### Nexx Garage Doors: The “Door” Part Being Optional

Security researcher Sam Sabatan has discovered multiple CVEs in Nexx smart home devices. [On his Medium blog](https://medium.com/@samsabetan/the-uninvited-guest-idors-garage-doors-and-stolen-secrets-e4b49e02dadc), Sam writes:

> In late 2022, while conducting independent security research, I discovered a series of critical vulnerabilities in Nexx’s smart device product line, which encompasses Smart Garage Door Openers, Alarms, and Plugs. These vulnerabilities enabled remote attackers to open and close garage doors, take control of alarms, and switch smart plugs on and off for any customer.
>
> I collaborated closely with The United States Department of Homeland Security Cybersecurity and Infrastructure Security Agency (“CISA”) to responsibly disclose the research results.

As a result of Sam’s disclosure, CISA assigned 5 new CVEs, the highest being a 9.3/10 due to hard-coded credentials.

Distressingly, Sam notes:

> Nexx has not replied to any correspondence from myself, DHS (CISA and US-CERT) or VICE Media Group. I have independently verified Nexx has purposefully ignored all our attempts to assist with remediation and has let these critical flaws continue to affect their customers.

Given that no remediation is available, Bleeping Computer [makes the following recommendation](https://www.bleepingcomputer.com/news/security/hackers-can-open-nexx-garage-doors-remotely-and-theres-no-fix/):

> In the meantime, to mitigate the risk from these attacks until a fixing patch is made available by the vendor, it is recommended to disable internet connectivity for your Nexx devices, place them behind firewalls, and isolate them from mission-critical networks.
>
> If it is necessary to access or control Nexx devices remotely, only do so through a VPN (virtual private network) connection that encrypts the data transmissions.

### Google Shores Up the Security of the Open Source Software Supply Chain

Google [notes that](https://cloud.google.com/blog/products/identity-security/google-cloud-assured-open-source-software-service-now-ga):

> 17% of all security breaches start with a supply chain attack, the initial infection vector second only to exploits.

In order to address this situation, Google has created a new service called “Assured Open Source Software (Assured OSS)“. Initially available for the Python and Java ecosystems:

> Assured OSS gives any organization that uses open source software the opportunity to leverage the security and experience Google applies to open source dependencies by incorporating the same OSS packages that Google secures and uses into their own developer workflows.

Google has been testing the service for about a year. Assured OSS works by:
> * continuously mirroring key external ecosystems to manage end-to-end security without creating forks
> * managing the security and integrity of the mirrored repos and end-to-end build tool chain with tamper-evident provenance and attestations
> * continuously scanning for, fuzz testing, and fixing critical vulnerabilities, which are then quickly contributed back upstream to limit the exposure time and blast radius
> * operating a critical patching team to support covered packages

It’s cool to see Google making this widely available as it will likely increase the security of a lot of Python and Java applications:

> There are significant security benefits to Assured OSS adopters and the larger community from the curation process. Since our Assured OSS team curated the first 278 packages, we have been the first to find 48% of the new vulnerabilities (CVE) — each of these CVEs has been fixed and upstreamed.

### Cloudy with a Chance of Microsoft

Microsoft has switched to a [new naming methodology](https://learn.microsoft.com/en-us/microsoft-365/security/intelligence/microsoft-threat-actor-naming?view=o365-worldwide) for threat actors, using weather-themed names. Under the new scheme, Russia is “Blizzard”, China is “Typhoon”, and Iran is “Sandstorm.” The system also has names for different threat actor motivation categories. For example, “Tempest” refers to attackers who are financially motivated.

The new system replaces Microsoft’s old naming scheme (listed in the above article) and looks to be much more cohesive and understandable.

## A Few PSAs...
- [Google Authenticator now supports Google Account synchronization; E2E encryption forthcoming](https://security.googleblog.com/2023/04/google-authenticator-now-supports.html)
- [Denver FBI Issues Malware Warning on Public Device Charging](https://www.govtech.com/security/denver-fbi-issues-malware-warning-on-public-device-charging):


## Other Software with Critical Patches Available
- This month, Apple [patched two 0-days in iOS 16 and macOS Ventura](https://isc.sans.edu/diary/Apple+Patching+Two+0Day+Vulnerabilities+in+iOS+and+macOS/29726). They also released [security patches for iOS 15](https://support.apple.com/en-us/HT201222), so check for updates if you’ve got any older Apple devices still in use.
- Adobe [patched a number of security flaws](https://helpx.adobe.com/security/security-bulletin.html) in multiple products, including Reader.
- Microsoft’s monthly patch Tuesday was April 11. In it, “we got patches for 114 vulnerabilities. Of these, 7 are critical, and 1 is already being exploited, according to Microsoft.” [source](https://isc.sans.edu/diary/Microsoft+April+2023+Patch+Tuesday/29736)


## Deep Dives
A few interesting deep-dive reads from the month:
- [The Car Thieves Using Tech Disguised Inside Old Nokia Phones and Bluetooth Speakers](https://www.vice.com/en/article/v7beyj/car-thieves-tech-hidden-old-nokia-phones-bluetooth-speakers-emergency-engine-start-keyless)
- [Calculating CVSS Scores with ChatGPT](https://isc.sans.edu/diary/Calculating+CVSS+Scores+with+ChatGPT/29774)
- [Lazarus hackers now push Linux malware via fake job offers](https://www.bleepingcomputer.com/news/security/lazarus-hackers-now-push-linux-malware-via-fake-job-offers/)
- [Discarded, not destroyed: Old routers reveal corporate secrets](https://www.welivesecurity.com/2023/04/18/discarded-not-destroyed-old-routers-reveal-corporate-secrets/)


## Learning -- Monitor Data Breaches for Your Personal Information

Want to know if an email address you own has been compromised in a data breach? There are a few great, free options out there.

First off, Mozilla has a nifty tool you might want to check out: The Firefox Monitor Breach Database.

> We monitor all known data breaches to find out if your personal information was compromised. Here’s a complete list of all of the breaches that have been reported since 2007.

The free tool is available here: [https://monitor.firefox.com/breaches](https://monitor.firefox.com/breaches). You can receive a notification should any email address you own be compromised in a data breach by signing up for the free Firefox Monitor service here: [https://monitor.firefox.com](https://monitor.firefox.com).

Additionally, the OG breach monitoring site is [';--have i been pwned?](https://haveibeenpwned.com). Created and run by Troy Hunt, the free site first launched back in 2013 and alerts users should any of their registered email addresses show up in a data breach.

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)
* [https://en.wikipedia.org/wiki/Have_I_Been_Pwned%3F](https://en.wikipedia.org/wiki/Have_I_Been_Pwned%3F)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏻‍💻 🌐 👨🏾‍💻
