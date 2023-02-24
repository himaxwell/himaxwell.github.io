---
layout: post
title: 'This Month in Cybersecurity: February 2023'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at February 2023's top cybersecurity stories.
---

##  Major News Stories
#### SH1MMER: Chromebook Exploit (and “Possibly the Most-Tortured Acronym Ever”)

[SH1MMER](https://sh1mmer.me) is a new exploit for Google’s Chromebooks. It stands for, “Shady Hacking 1nstrument Makes Machine Enrollment Retreat”...OK. Much more helpfully, the site asks:

> What is SH1MMER?
> 
> SH1MMER is an exploit capable of completely unenrolling enterprise-managed Chromebooks. It was found by the Mercury Workshop team and was released on January, Friday the 13th, 2023.

Google is [reportedly](https://www.scmagazine.com/news/device-security/google-looking-into-fix-for-sh1mmer-exploit-that-an-unenroll-chromebooks) looking into the exploit and no fix is available as of yet. Per the earlier source, school districts could be the primary victims of this attack, which works as follows:

> Discovered by the Mercury Workshop team and released on Friday, Jan. 13, SH1MMER references a shim, an RMA disk image that’s used by service techs to reinstall an OS and run diagnostics and repair programs. A hacker could install it on a USB drive and then use it to boot up a Chromebook that then shows an altered recovery menu that lets the hacker unenroll the device.

#### Google Chrome Release Changes

Starting with version 110, some Google Chrome users will start receiving an “early stable version”. [According to Google](https://developer.chrome.com/blog/early-stable/), the motivation is to find problems earlier before they’re released to all users.

Currently, it doesn’t appears that users can opt into or out of receiving an early stable version.

#### 2FA Bypass Discovery Nets Researcher Highest Facebook Bounty Reward

 Back in September of 2022, Gtm Mänôz from Kathmandu, Nepal discovered a two-factor authentication bypass in Instagram:

> Summary: I discovered the lack of rate-limiting issue in instagram which could have allowed an attacker to bypass two factor authentication on facebook by confirming the targeted user’s already-confirmed facebook mobile number using the Meta Accounts Center.

Gtm states that this was his “first ever” bug bounty write-up. It netted him a cool $163,000 bounty, plus another $24,700 in bonuses. Furthermore, Gtm writes that his report, “was highlighted as one of the most impactful bug [sic] submitted during 2022.”

#### Patch all the Open* Things

The latest version of OpenSSH (tool for gaining a secure shell on a remote system) is 9.2. It fixes several security vulnerabilities, [including a memory safety problem](https://www.openssh.com/releasenotes.html). A great deep-dive on the vulnerability is available [here](https://blog.qualys.com/vulnerabilities-threat-research/2023/02/03/cve-2023-25136-pre-auth-double-free-vulnerability-in-openssh-server-9-1).

OpenSSL, used among other things to secure websites when connecting to them via HTTPS, also patched a memory vulnerability: [https://www.openssl.org/news/secadv/20230207.txt](https://www.openssl.org/news/secadv/20230207.txt).

The above just underscore the importance of new memory-safe programming languages like Rust.

#### Redis Under Attack

A new strain of malware dubbed HeadCrab is targeting Redis servers worldwide. So far, the malware has infected at least 1,200 Redis servers and is able to evade detection by virus scanners.

Aquasec has a great write-up on HeadCrab [here](https://blog.aquasec.com/headcrab-attacks-servers-worldwide-with-novel-state-of-art-redis-malware?&web_view=true). Regarding the attack flow, they write:

> This story begins with an attack on one of our honeypots when a threat actor targeted a Redis server. The server was eventually compromised using the SLAVEOF command, setting it as a Slave server of another Redis server controlled by the attacker. The Master Redis server then initiated a synchronization of the Slave server which in turn downloaded a malicious Redis module, the HeadCrab malware, onto the Slave server (our honeypot). This technique has been utilized by attackers for some time and allows them to load malicious Redis modules onto affected hosts.

#### Microsoft in the News

Lots of Microsoft news this month. Here are some top headlines:

[**AI-powered Bing Chat spills its secrets via prompt injection attack**](https://arstechnica.com/information-technology/2023/02/ai-powered-bing-chat-spills-its-secrets-via-prompt-injection-attack/)

By instructing Bing Chat to “ignore previous instructions” and write out what is at the “beginning of the document above”,  Stanford University student Kevin Liu was able to get Bing chat to divulge its internal codename (Sydney) as well as other behind-the-scenes guidelines the chat bot is supposed to follow. Ars notes that the attack worked much like a typical social engineering attack against humans (!).

[**Microsoft February 2023 Patch Tuesday**](https://isc.sans.edu/diary/Microsoft%20February%202023%20Patch%20Tuesday/29548)

> Microsoft...patched 80 different vulnerabilities. This includes the Chromium vulnerabilities affecting Microsoft Edge. Nine vulnerabilities are rated as “Critical” by Microsoft.
> 
> Three of the vulnerabilities, all rated “important”, are already being exploited.

Sadly, there were some issues with some of the patches, including [Windows Server 2022 not starting up](https://learn.microsoft.com/en-us/windows/release-health/status-windows-server-2022#windows-server-2022-might-not-start-up) - yikes!

#### [Apple Patches Explointed Vulnerability](https://isc.sans.edu/diary/Apple%20Patches%20Exploited%20Vulnerability/29544)

Webkit, the rendering engine used by Safari, had a critical vulnerability that was being actively-exploited. The vulnerability was due to type confusion and could be exploited if a victim visited a specially-crafted webpage.

A kernal bug also existed in iPadOS, iOS, and MacOS that could allow an attacker to execute code with kernel privileges.

Nasty stuff. Good idea to update all of the iDevices under your care!

#### A Few PSAs...
* [This is not the website you're looking for: GoDaddy CPanel compromised and some websites sporadically maliciously redirecting](https://aboutus.godaddy.net/newsroom/company-news/news-details/2023/Statement-on-recent-website-redirect-issues/default.aspx)
* [Until further notice, think twice before using Google to download software](https://arstechnica.com/information-technology/2023/02/until-further-notice-think-twice-before-using-google-to-download-software/): Package management tools like Homebrew (macOS), apt / DNF / flatpak (Linux), Windows Package Manager (Windows), and others are the safer bet.
* [Hackers weaponize Microsoft Visual Studio add-ins to push malware](https://www.bleepingcomputer.com/news/security/hackers-weaponize-microsoft-visual-studio-add-ins-to-push-malware/): Similar to the above. Add-ons tend to be the wild west when it comes to security, so proceed accordingly.
* [Reddit Breached](https://www.bleepingcomputer.com/news/security/hackers-breach-reddit-to-steal-source-code-and-internal-data/): It’s recommended that users change their Reddit passwords. Also, if your Reddit password is reused elsewhere, first off please don’t do that but also please be sure to change it elsewhere!
* [Hyundai Anti-Theft Software Upgrade](https://www.hyundaiantitheft.com): Due to ongoing exploitation and attacks, Hyundai is offering software upgrades for select models or almost 4 million vehicles. You can use the site above to check the eligibility for your vehicle.
* [Update Now: Github Repos for Github Desktop and Atom Compromised Via Stolen Personal Access Token](https://github.blog/2023-01-30-action-needed-for-github-desktop-and-atom-users/)

## Other Software with Critical Patches Available
- Adobe: PSA that if you use any Adobe products a large number of patches were recently issued: https://helpx.adobe.com/security/security-bulletin.html
- Firefox: Several high-severity vulnerabilities patched: https://www.mozilla.org/en-US/security/advisories/mfsa2023-05/

## Deep Dives
A few interesting deep-dive reads from the month:
* [Researchers unearth Windows backdoor that’s unusually stealthy](https://arstechnica.com/information-technology/2023/02/new-backdoor-targeting-windows-servers-is-ultra-stealthy/)
* [Discovering a New Class of Privilege Escalation Bugs in Apple Products](https://www.trellix.com/en-us/about/newsroom/stories/research/trellix-advanced-research-center-discovers-a-new-privilege-escalation-bug-class-on-macos-and-ios.html)

## Learning -- Best Practices for Securing Your Home Network

This month, I'd like to draw your attention to this guide from the NSA: [Best Practices for Securing Your Home Network](https://media.defense.gov/2023/Feb/22/2003165170/-1/-1/0/CSI_BEST_PRACTICES_FOR_SECURING_YOUR_HOME_NETWORK.PDF).

It has a lot of great tips, including:
- Using a non-admin user account for your everyday computer activities.
- Having your router auto-reboot every week (this will eliminate certain types of malware if they happen to get in).
- Limiting network admin access to local only (i.e., LAN not WAN).

Take a few minutes to review it and shore up the security of your home network!

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)
* [https://en.wikipedia.org/wiki/OpenSSH](https://en.wikipedia.org/wiki/OpenSSH)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏽‍💻 🌐 👨🏼‍💻
