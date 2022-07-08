---
layout: post
title: 'This Week in Cybersecurity: July 03-09, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---
## Important Update
First, thanks to everyone who's taken the time to read this weekly post since it launched in April. Hopefully, you've found it to be helpful and informative.

Moving forward, there are going to be some changes but don't worry - we're not going anywhere, just changing the cadence a bit. Starting next week, this series will become "This _Month_ in Cybersecurity" and new posts will release on the last Friday of the month. So we'll see you again on Friday, July 29!

##  Major News Stories
* This week, Google released an important update for Google Chrome on desktop that addressed `CVE-2022-2294`. According to the [blog post](https://chromereleases.googleblog.com/2022/07/extended-stable-channel-update-for.html), "Google is aware that an exploit for CVE-2022-2294 exists in the wild." Details about the vulnerability are scant, with blog post links leading to "Access Denied" pages (at the time of writing). Regarding actively exploited 0-days, Google has [previously stated](https://chromereleases.googleblog.com/2022/03/stable-channel-update-for-desktop_25.html), "Access to bug details and links may be kept restricted until a majority of users are updated with a fix", so it seems like this one warrants updating any of your Chrome desktop instances with urgency. Instructions for doing so are available here: [https://support.google.com/chrome/answer/95414](https://support.google.com/chrome/answer/95414).
* This week, the bug bounty platform HackerOne [terminated an employee ](https://www.bleepingcomputer.com/news/security/rogue-hackerone-employee-steals-bug-reports-to-sell-on-the-side/) for stealing bug reports and selling them on the side. "The rogue worker had contacted about half a dozen HackerOne customers and collected bounties "in a handful of disclosures," the company said."
* Apple has announced plans for adding a "Lockdown Mode" to some of its products. [According to Apple](https://www.apple.com/newsroom/2022/07/apple-expands-commitment-to-protect-users-from-mercenary-spyware/), Lockdown Mode sharply reduces the potential attack surface of its devices by locking down or disabling a number of features, including message attachments, link previews, incoming FaceTime calls from unknown contacts, and wired connections with a computer or accessory, to name a few. Lockdown Mode is targeted at, "the very few users who...may be personally targeted by some of the most sophisticated digital threats" and is expected to be available in iOS 16, iPadOS 16, and macOS Ventura.
* A few interesting deep-dive reads from the week:
  * [NPM supply-chain attack impacts hundreds of websites and apps](https://www.bleepingcomputer.com/news/security/npm-supply-chain-attack-impacts-hundreds-of-websites-and-apps/)

## Other Software with Critical Patches Available
* Fortinet, a cybersecurity vendor, patched a number of critical issues in its products in its [July update](https://fortiguard.fortinet.com/psirt?date=07-2022).

## Learning -- Secure Settings for Your Home Router
Sadly, many vendors ship routers with default settings that aren't ideal. Here are a few router settings you can tweak to make your home network a bit more secure.

The following list is by no means exhaustive, but should hopefully provide a good starting point for most users. Please see your router's user manual for instructions on how to access its admin web interface and change these settings:
1. **Change the default admin password.** Most routers have a hard-coded password for the admin user on a sticker on the bottom of the router. It's a good idea to change this to something random that you write down, preferably in a password manager.
1. **Make sure your router is set to automatically update its firmware.** These updates often contain critical security fixes.
1. **Don't user your ISP's DNS server.** ISPs often track customers via their DNS servers, so considering setting your router to use any one of the many awesome free DNS services out there, like [Quad9](https://www.quad9.net/) or [AdGuard DNS](https://adguard-dns.io/en/welcome.html).
1. **Turn off Universal Plug and Play (UPnP).** Here's a quick rundown of what UPnP is and why it's best to turn it off: [https://www.upguard.com/blog/what-is-upnp](https://www.upguard.com/blog/what-is-upnp)
1. **Turn off Wi-Fi Protected Setup (WPS).** This is another insecure protocol. Disabling it reduces your attack surface: [https://nakedsecurity.sophos.com/2011/12/30/most-wi-fi-routers-susceptible-to-hacking-through-security-feature/](https://nakedsecurity.sophos.com/2011/12/30/most-wi-fi-routers-susceptible-to-hacking-through-security-feature/)
1. **Make sure your router can filter bad stuff.** Make sure your router's firewall is turned _on_ and that network address translation (NAT) is _enabled_.
1. **Make sure your router's admin interface isn't accessible on the internet (i.e., accessible via the WAN).** While many routers offer administration access via the internet for convenience, turning this feature off will prevent someone not on your local wifi/ethernet network from being able to access/change your router's settings.

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://arstechnica.com/information-technology/2022/07/introducing-lockdown-from-apple-the-coolest-defense-youll-probably-never-use/](https://arstechnica.com/information-technology/2022/07/introducing-lockdown-from-apple-the-coolest-defense-youll-probably-never-use/)
* [https://twit.tv/shows/security-now/episodes/878](https://twit.tv/shows/security-now/episodes/878)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏾‍💻 🌐 👨🏼‍💻
