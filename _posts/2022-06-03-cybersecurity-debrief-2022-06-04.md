---
layout: post
title: 'This Week in Cybersecurity: May 29 - June 04, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---

##  Major News Stories
* This week turned out to be a bad one for Microsoft protocols.
  * Things kicked off when researchers reported an [entirely new attack vector for Microsoft Office](https://isc.sans.edu/forums/diary/New+Microsoft+Office+Attack+Vector+via+msmsdt+Protocol+Scheme/28694/).
    * The attack was dubbed "Follina" and exploits the `ms-msdt:/` protocol.
    * From the SANS article above, "msdt.exe is a tool provided by Microsoft that will collect information to send to Microsoft Support. Microsoft Office will automatically process the MSDT URL and execute [any Powershell payloads]." Yikes!
    * To mitigate this vulnerability, [Microsoft recommends disabling the `ms-msdt` URL protocol](https://msrc-blog.microsoft.com/2022/05/30/guidance-for-cve-2022-30190-microsoft-support-diagnostic-tool-vulnerability/).
  * Additionally, [a 0-day was discovered in the Windows Search protocol](https://www.bleepingcomputer.com/news/security/new-windows-search-zero-day-added-to-microsoft-protocol-nightmare/).
    * The attack works by leveraging the `search-ms` URI protocol handler to, "Open a search window containing remotely-hosted malware executables simply by launching a Word document."
    * As a mitigation, Microsoft recommends, "Users practice safe computing habits and to only open files that come from trusted sources."
* [NPM now requires 2FA for maintainers of its top 500 packages](https://github.blog/changelog/2022-05-31-top-500-npm-package-maintainers-now-require-2fa/). This move follows on the heels of successful penetration tests of NPM over the past several weeks, where expired domain names were used to hijack email addresses and take ownership of packages.
* [A 0-day was discovered in Atlassian Confluence](https://www.volexity.com/blog/2022/06/02/zero-day-exploitation-of-atlassian-confluence/). Unfortunately, "There is currently no available patch or fix for the issue described in this blog post. Volexity strongly recommends that all organizations block external access to their Confluence Server instances immediately until an update is provided by Atlassian."
* A few interesting deep-dive reads from the week:
  * [Over 3.6 million MySQL servers found exposed on the Internet](https://www.bleepingcomputer.com/news/security/over-36-million-mysql-servers-found-exposed-on-the-internet/)

## Other Software with Critical Patches Available
* The [Open Automation Software Platform](https://blog.talosintelligence.com/2022/05/vuln-spotlight-open-automation-platform.html) had 8 CVEs patched.

## Learning -- Defense In Depth: Strategies
[Last week]({% link _posts/2022-05-27-cybersecurity-debrief-2022-05-28.md %}), we discussed the _what_ and _why_ of defense-in-depth. This week, we'll discuss the _how_, looking at three practical strategies everyday computer users can easily deploy to improve their cybersecurity.

First, consider making your daily computer user a non-administrative (standard) user. Unfortunately, when you first set up your computer, most operating systems will make your user one with root/administrative permissions by default. However, if all you do on your computer is email, web browsing, word processing, etc. there's no need for your user to have admin privileges. Instead, consider creating a new user for your computer, giving that user admin privileges, removing admin privileges from your daily user, and then using the admin user whenever you need to do anything admin-related on your computer (also, most operating systems will prompt you to enter the admin username/password when performing an admin-only action when logged in as a standard user). Not running as an admin-enabled user by default is a good defense-in-depth practice since, if your computer were to be compromised, an attacker wouldn't automatically gain admin privileges on your computer (most breaches grant an attacker only the same access/permissions as the compromised user).

Next, enable 2-factor authentication (2FA) wherever you can. [PC Magazine has a great intro to 2FA and list of steps for enabling 2FA for top websites available here](https://www.pcmag.com/how-to/multi-factor-authentication-2fa-who-has-it-and-how-to-set-it-up). As stated in the article, prefer using an authenticator application to SMS/text message as SMS is not very secure. 2FA is a good defense-in-depth practice since a password breach won't automatically grant an attacker access to your account.

Finally, adopt a defense-in-depth mindset. Most importantly, this means becoming _comfortable_ with being _uncomfortable_. Enhancing your cybersecurity with defense-in-depth practices means that it will take a bit more work to do certain things, various daily tasks will have a bit more friction, and you'll have to keep track of few more moving parts. But, in the event of a breach, all that extra effort will pay off when an attacker finds themselves faced, not with unlimited access to your data, network, and/or systems, but instead with yet another line of defense that must be overcome.

There's a good chance an attacker is looking for a victim, not a fight. Defense-in-depth strategies increase the probability that an attacker will expose themselves or give up, plus they buy you time - time to uncover an attack and respond. Defense-in-depth helps you win the fight before an attack happens. In the words of Sun Tzu, "Plan for what is difficult while it is easy, do what is great while it is small." (Sun Tzu, _The Art of War_)

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏻‍💻 🌐 👨🏿‍💻
