---
layout: post
title: 'This Month in Cybersecurity: March 2023'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at March 2023's top cybersecurity stories.
---

##  Major News Stories
#### AI is Having a Moment
It's hard not to run into AI-themed news these days. Sadly, security has so far been one of the less-publicized sides of the recent AI boom brought on by ChatGPT. However, the powerful software has many security implications. A few headlines to think about include:

##### [Experts call for pause on AI training citing risks to humanity](https://www.bleepingcomputer.com/news/technology/experts-call-for-pause-on-ai-training-citing-risks-to-humanity/)
"Over a thousand people, including professors and AI developers, have co-signed an open letter to all artificial intelligence labs, calling them to pause the development and training of AI systems more powerful than GPT-4 for at least six months."

##### [ChatGPT leaks user credit card details](https://cybernews.com/news/payment-info-leaked-openai-chatgpt-outage/)
Conversation titles were also leaked and the bug was due to an issue in the `redis-py` library, one of ChatGPT's dependencies.

##### [Italian privacy regulator bans ChatGPT](https://www.politico.eu/article/italian-privacy-regulator-bans-chatgpt/)
> The [Italian] national data protection authority said it will immediately block and investigate OpenAI, the U.S. company behind the popular artificial intelligence tool, from processing the data of Italian users. The order is temporary until the company respects the EU's landmark privacy law, the General Data Protection Regulation (GDPR).

##### [Fake ChatGPT Chrome extension targeted Facebook Ad accounts](https://www.helpnetsecurity.com/2023/03/09/fake-chatgpt-extension/)

> While the extension does connect with ChatGPT’s API, it also harvests information from users’ browsers, stealing cookies of authorized, active sessions to any service they have and employing tailored tactics to take over the user’s Facebook accounts.

---

There's no telling how the current AI moment will play out, whether we're at an inflection point or if the buzz will die down, but companies looking to adopt AI tech would do well not to feed it any data they wouldn't normally make publicly available, at least until the technology has a bit more of a track record and the default security and privacy posture of AI companies becomes more standardized.

#### 3CX Pwnd
Here's a company with over 12 million daily users you probably haven't heard of: 3CX. The company makes VoIP/PBX software, which was recently the victim of a supply chain attack. [Ars reports](https://arstechnica.com/information-technology/2023/03/3cx-knew-its-app-was-flagged-as-malicious-but-took-no-action-for-7-days/):

> A threat group tied to the North Korean government compromised the 3CX software build system and used the control to push Trojanized versions of the company’s DesktopApp programs for Windows and macOS. The malware causes infected machines to beacon to actor-controlled servers and, depending on unknown criteria, the deployment of second-stage payloads to specific targets. In a few cases, the attackers carried out “hands-on-keyboard activity” on infected machines, meaning the attackers manually ran commands on them.

The big issue here is that when security software initially began flagging 3CX's software as malicious, the company at first took no action, then blamed the security software before finally confirming that several versions of their app did indeed have security issues. This is a good reminder not to immediately cry "false positive" when security software begins raising alarms.

#### LastPass Incident Updates
LastPass has published more details on its most-recent security breach here:

* https://support.lastpass.com/help/incident-1-additional-details-of-the-attack
* https://support.lastpass.com/help/incident-2-additional-details-of-the-attack

One key quote from the above, where it’s stated that the attacker was inside LastPass’s cloud for over two months:

> Our investigation has revealed that the threat actor pivoted from the first incident, which ended on August 12, 2022, but was actively engaged in a new series of reconnaissance, enumeration, and exfiltration activities aligned to the cloud storage environment spanning from August 12, 2022 to October 26, 2022.

At this point, it’s probably best that any LastPass customers move to a new password manager as LastPass has a pretty spotty track record when it comes to security, not something you want to hear about your password manager.

#### iCompromise via iPhone Passcode
This one has been getting a lot of attention recently. I’m not quite sure it deserves this amount of hype, but it’s good to note.

The exploit goes like this: If an attacker can observe you entering your iPhone passcode and then get access to your iPhone, they can theoretically take over your iCloud account via an iCloud password reset, which only requires the phone passcode (and not the previous password) to perform. Since iCloud contains passwords, payment details, phone backups, etc. this is obviously bad.

This is somewhat of a social engineering attack as most of the reported instances of this exploit have been reported in larger cities like New York at venues like bars:

> Groups of two or three thieves would go to a bar and befriend the victims to try and access their iPhones. If they couldn’t watch the victim type in their passcode, the thieves might try to get them to open a social media app or have the victim hand over their phone for a picture.

More info in the AppleInsider article [here](https://appleinsider.com/articles/23/02/24/if-both-your-iphone-and-passcode-get-stolen-youre-in-deep-trouble), including some common sense ways to protect yourself, probably the biggest being don’t ever hand your unlocked iPhone to a stranger.

#### Google Chrome Enhanced Protection
PSA: Google Chrome has an optional “enhanced protection” mode that can be enabled. Features of this mode include:
* Real time URL checks
* File checks before downloading
* More advanced vision-based phishing detection

Looks like this mode is not enabled by default since it sends a lot more potentially personally identifiable data to Google. That said, if you are comfortable with that:

> Safe Browsing’s Enhanced Protection is currently available for all desktop platforms, Android devices and now iOS mobile devices. It can be enabled by navigating to the Privacy and Security option located in Chrome settings.

More details are available on Google’s blog here: https://security.googleblog.com/2022/12/enhanced-protection-strongest-level-of.html

#### A Bad Month for [Redacted] Images

Begun the “acropalypse” has. It all started mid-March, when security researchers David Buchanan and Simon Aarons found that Google Pixel phones kept original image data around, even if they’d been cropped or edited. The flaw was dubbed “acropalypse”, and, as [Bleeping Computer explains](https://www.bleepingcomputer.com/news/microsoft/windows-11-snipping-tool-privacy-bug-exposes-cropped-image-content/):

> Poses a significant privacy concern as if a user shares a picture, such as a credit card with a redacted number or revealing photos with the face removed, it may be possible to partially recover the original photo.

You can check images for data leakage using the online tool the researchers created: https://acropalypse.app.

But the bad news didn’t stop there. As it turns out, this flaw also affects the Windows 11 Snipping Tool. The issue arises when saving an image edited with the Windows 11 Snipping Tool - the unedited image data remains behind and is at least partially recoverable.

Microsoft [has since patched the flaw](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-acropalypse-privacy-bug-in-windows-11-snipping-tool/). Android appears to still be vulnerable.

For the curious, here are a few more links:
* Wikipedia has a great deep-dive on the bug [here](https://en.wikipedia.org/wiki/ACropalypse) as well as more technical details on its underlying causes.
* [This Github repo](https://github.com/infobyte/CVE-2023-21036) has a handy collection of scripts for detecting and mitigating acropalypse.
* SANS has released a [guide on how to safely crop and redact images](https://isc.sans.edu/diary/Cropping%20and%20Redacting%20Images%20Safely/29666).

#### A Few PSAs...
* [GitHub.com rotates its exposed private SSH key](https://www.bleepingcomputer.com/news/security/githubcom-rotates-its-exposed-private-ssh-key/): "Users should update their ~/.ssh/known_hosts file with GitHub's new key fingerprint, otherwise they may see security warnings when making SSH connections. When receiving such warnings, users should ensure the fingerprint seen on their screen matches the one for GitHub.com's latest key."
* [QNAP warns customers to patch Linux Sudo flaw in NAS devices](https://www.bleepingcomputer.com/news/security/qnap-warns-customers-to-patch-linux-sudo-flaw-in-nas-devices/): Patch your QNAP NAS devices now!
* [Google finds more Android, iOS zero-days used to install spyware](https://www.bleepingcomputer.com/news/security/google-finds-more-android-ios-zero-days-used-to-install-spyware/): Apparently the attack vector here is bit.ly links sent via text message, so be wary of any you may receive.
- [WiFi protocol flaw allows attackers to hijack network traffic](https://www.bleepingcomputer.com/news/security/wifi-protocol-flaw-allows-attackers-to-hijack-network-traffic/): Not actively-exploited, but attacks only ever get better...
- [Stealthy UEFI malware bypassing Secure Boot enabled by unpatchable Windows flaw: BlackLotus represents a major milestone in the continuing evolution of UEFI bootkits](https://arstechnica.com/information-technology/2023/03/unkillable-uefi-malware-bypassing-secure-boot-enabled-by-unpatchable-windows-flaw/): “The world’s first-known instance of real-world malware that can hijack a computer’s boot process even when Secure Boot and other advanced protections are enabled and running on fully updated versions of Windows.”

## Other Software with Critical Patches Available
- [Zoom Patches](https://explore.zoom.us/en/trust/security/security-bulletin/): High severity issues seem to mainly affect Windows.
- [Microsoft March 2023 Patch Tuesday](https://isc.sans.edu/diary/Microsoft%20March%202023%20Patch%20Tuesday/29634): “This month we got patches for 76 vulnerabilities. Of these, 9 are critical and 2 are already being exploited, according to Microsoft.”
- [Apple Updates Everything (including Studio Display)](https://isc.sans.edu/diary/Apple%20Updates%20Everything%20%28including%20Studio%20Display%29/29682)


## Deep Dives
A few interesting deep-dive reads from the month:
* [How SMS Fraud Works and How to Guard Against It](https://apuchitnis.substack.com/p/how-sms-fraud-works-and-how-to-guard-against-it)
* [Hackers Claim They Breached T-Mobile More Than 100 Times in 2022](https://krebsonsecurity.com/2023/02/hackers-claim-they-breached-t-mobile-more-than-100-times-in-2022/)
* [Mozilla Firefox gets built-in Firefox Relay (email privacy / protection system) controls](https://www.bleepingcomputer.com/news/security/mozilla-firefox-gets-built-in-firefox-relay-controls/)

## Learning -- `CVE-2008-5189`
On Sunday, October 19, 2008, the Tampa Bay Rays beat the Boston Red Sox, 4 games to 3 to win the MLB American League Championship. Also on that day, DHH published [a short blog post](https://rubyonrails.org/2008/10/19/rails-2-0-5-redirect_to-and-offset-limit-sanitizing) on the Ruby on Rails blog, mentioning that Rails 2.0.5 had been released, partially to address a "Response Splitting" attack. DHH linked to [another Rails blog post published on the same day])(https://rubyonrails.org/2008/10/19/response-splitting-risk) which explains the issue:

> The Ruby HTTP libraries used by Rails do not perform any santization of the values of their HTTP Headers. This can lead to Response Splitting and Header Injection attacks in certain circumstances where user-provided values are written into response headers. These malformed values can be used to set custom cookies, and forge fake responses to users if your application uses any of the user submitted parameters to construct HTTP headers without sanitizing.

> A common scenario where this can be exploited is where your application takes a URL from the query string, and redirects the user to it. To mitigate this common scenario new versions of Rails will be released which sanitize the values passed to redirect_to. However you will still need to take care when writing other values to response headers.

`CVE-2008-5189` wouldn't actually be published until the following month on November 20, 2008. By then, the Rays had fallen to the Philadelphia Phillies, losing 4 games to 1, and, as of this writing, the Rays have yet to win a World Series.

That said, `CVE-2008-5189` didn't prove to be an all-star either, as it only earned itself a CVSS score of 5/10. The official vulnerability description reads:

> CRLF injection vulnerability in Ruby on Rails before 2.0.5 allows remote attackers to inject arbitrary HTTP headers and conduct HTTP response splitting attacks via a crafted URL to the redirect_to function.

Key takeaway: Always sanitize your HTTP headers kids!

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)
* [https://en.wikipedia.org/wiki/OpenSSH](https://en.wikipedia.org/wiki/OpenSSH)
* [https://arstechnica.com/information-technology/2023/03/massive-supply-chain-attack-with-ties-to-north-korea-hits-users-of-3cx-voice-app/](https://arstechnica.com/information-technology/2023/03/massive-supply-chain-attack-with-ties-to-north-korea-hits-users-of-3cx-voice-app/)
* [https://www.onthisday.com/date/2008/october/19](https://www.onthisday.com/date/2008/october/19)
* [https://en.wikipedia.org/wiki/Tampa_Bay_Rays](https://en.wikipedia.org/wiki/Tampa_Bay_Rays)
* [https://en.wikipedia.org/wiki/2008_World_Series](https://en.wikipedia.org/wiki/2008_World_Series)
* [https://en.wikipedia.org/wiki/2008_Tampa_Bay_Rays_season](https://en.wikipedia.org/wiki/2008_Tampa_Bay_Rays_season)
* [https://nvd.nist.gov/vuln/detail/CVE-2008-5189](https://nvd.nist.gov/vuln/detail/CVE-2008-5189)
* [https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-5189](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-5189)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏼‍💻 🌐 👨🏽‍💻
