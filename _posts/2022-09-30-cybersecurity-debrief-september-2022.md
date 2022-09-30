---
layout: post
title: 'This Month in Cybersecurity: September 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at September 2022's top cybersecurity stories.
---

##  Major News Stories
#### iOS 12 Lives!
On August 31, 2022, Apple released iOS version 12.5.6. This is notable since iOS 12 was originally released on September 17, 2018, or almost 4 years ago. The last update this iOS version saw was released in September of 2021, but an actively-exploited vulnerability prompted Apple to push a patch: “Impact: Processing maliciously crafted web content may lead to arbitrary code execution. Apple is aware of a report that this issue may have been actively exploited.” ([https://support.apple.com/en-us/HT213428](https://support.apple.com/en-us/HT213428))

#### LastPass Breached
On August 25, the popular password manager LastPass posted a notice [on its blog](https://blog.lastpass.com/2022/08/notice-of-recent-security-incident/) stating that it was breached and some of its source code leaked. Although the issue doesn’t appear to affect customers’ passwords, it might not be a bad idea for LastPass users to reset their master password.

#### Malicious Gifs = Malgificent?
A new report shows how attackers could leverage multiple vulnerabilities in the Microsoft Teams chat application to gain a reverse shell on victim machines. The attack vector? Gifs of course! The attack is very sophisticated and chains together numerous flaws in MS Teams. Check out the article on Bleeping Computer [here](https://www.bleepingcomputer.com/news/security/gifshell-attack-creates-reverse-shell-using-microsoft-teams-gifs/).

#### Github PRs as a Possible Attack Vector
Legit Security [reports](https://www.legitsecurity.com/blog/bypassing-github-required-reviewers-to-submit-malicious-code) on a unique way attackers may be able to leverage Github PRs to introduce malicious code into a codebase:
> TL;DR
> 
> GitHub’s required reviewers capability can be bypassed if currently using this setting to require at least one code review before merging code.
> 
> Any code reviewer reviewing code can simply submit malicious code on pull requests during the review process and merge that code to the main branch without review.
> 
> GitHub does not currently provide users the ability to directly eliminate this risk.

#### The "Truth is Often Stranger than Fiction" Section?
I'll just leave these here:
* "[Uber apparently hacked by teen, employees thought it was a joke](https://www.theverge.com/2022/9/16/23356213/uber-hack-teen-slack-google-cloud-credentials-powershell)"
* The DOJ has released an indictment against three Iranians who they say hacked US companies and [sent ransom demands to printers](https://arstechnica.com/tech-policy/2022/09/iranians-hacked-us-companies-sent-ransom-demands-to-printers-indictment-says/). Points for most creative ransom note delivery method I guess?

## Other Software with Critical Patches Available
* [Google Chrome patched at least one actively-exploited 0-day in September](https://chromereleases.googleblog.com/2022/09/stable-channel-update-for-desktop.html).
* The usual players [Apple](https://support.apple.com/en-us/HT201222), [Microsoft](https://isc.sans.edu/diary/Microsoft+September+2022+Patch+Tuesday/29044), and [Adobe](https://helpx.adobe.com/security/security-bulletin.html) all released important patches this month for their flagship products.

## Deep Dives
A few interesting deep-dive reads from the month:
* [PHP Deserialization Exploit Attempt: A Good Reminder to Never Trust Inputs](https://isc.sans.edu/diary/PHP+Deserialization+Exploit+attempt/29024)
* [Phishing Attacks Exploiting the Passing of Her Majesty Queen Elizabeth II](https://twitter.com/threatinsight/status/1570092339984584705)

## Learning -- A Friendly DNS Reminder
Next month, we'll resume our journey through the history of Ruby on Rails CVEs, but today I wanted to drop a friendly reminder re. DNS.

As I did some traveling over the past month, I was able to help friends and family with various technical issues/questions, and in the course of all this I was reminded of the unreasonable effectiveness of setting your home router to use one of the many awesome free DNS services out there. Using a privacy-respecting DNS service automatically protects virtually every single web request anyone on your network makes and it's an easy way to shed trackers and malware at your network border.

Here are some great DNS services for your consideration:
* [AdGuard DNS](https://adguard-dns.io/en/welcome.html)
* [Quad9](https://www.quad9.net/)
* [1.1.1.1 by Cloudflare](https://one.one.one.one/)
* [OpenDNS](https://www.opendns.com/)

A simple web search with your router's make and model + "change DNS server" should yield instructions on how to update your router's DNS server settings to use any of the above.

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)
* [AlternativeTo.net](https://alternativeto.net)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏽‍💻 🌐 🧑🏾‍💻
