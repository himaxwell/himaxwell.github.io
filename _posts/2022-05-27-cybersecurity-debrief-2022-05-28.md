---
layout: post
title: 'This Week in Cybersecurity: May 22-28, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---

##  Major News Stories
* After over a month of downtime due to a [serious security breach](https://status.heroku.com/incidents/2413), Heroku [this week re-enabled its Github integration](https://blog.heroku.com/github-integration-update). The restoration of this integration is significant since the breach originally happened, "On April 7, 2022, [when] a threat actor obtained access to a Heroku database and downloaded stored customer GitHub integration OAuth tokens."
* Recently, researchers exposed a vulnerability in NPM where several packages were taken over by registering the expired domain names used in maintainers' email addresses. This week, Python and PHP fell victim to a [similar attack](https://isc.sans.edu/forums/diary/ctx+Python+Library+Updated+with+Extra+Features/28678/). Even though AWS keys were stolen as part of the attack, the attacker [later claimed to be performing "research"](https://www.bleepingcomputer.com/news/security/hacker-says-hijacking-libraries-stealing-aws-keys-was-ethical-research/) and said the keys were not retained.
* Historically, the "Computer Fraud and Abuse Act of 1986" has been very broadly enforced, causing many white hat security researchers to fear that their good-faith research might result in criminal prosecution. This week, there was some welcome news on this front, with [the DOJ announcing](https://www.csoonline.com/article/3661591/doj-good-faith-security-research-won-t-be-charged-under-computer-fraud-and-abuse-act.html) that it, "Has revised its policy regarding charging violations of the Computer Fraud and Abuse Act (CFAA), stating that good faith security research does not warrant federal criminal action." However, white hats will want to remain aware of state and/or local laws surrounding their research, although this action by the DOJ provides a strong precedent that will hopefully eventually find its way to the local level.
* A few interesting deep-dive reads from the week:
  * [A "Zip Bomb" to Bypass Security Controls & Sandboxes](https://isc.sans.edu/forums/diary/A+Zip+Bomb+to+Bypass+Security+Controls+Sandboxes/28670/)
  * [How to find NPM dependencies vulnerable to account hijacking](https://www.theregister.com/2022/05/23/npm_dependencies_vulnerable/)

## Other Software with Critical Patches Available
* [Zoom patched several "High" severity CVEs](https://explore.zoom.us/en/trust/security/security-bulletin/)
* [Google Chrome patched 32 security issues, some of which were found at the May 2022 Pwn2Own competition](https://chromereleases.googleblog.com/2022/05/stable-channel-update-for-desktop_24.html)

## Learning -- Defense In Depth: Overview
Modern technology is extremely complex. For [example](https://helgeklein.com/blog/windows-os-services-apps-network-connection-target-hosts/), "The Microsoft Windows operating system talks to 291 hosts and 2,764 IPs on the internet." Given that the typical network will likely have multiple Windows, Mac, Linux, plus mobile OSes connected to it, it's easy to see how this complexity can grow exponentially.

Given this technological complexity facing governments, companies, and individuals, the cliche, "Don't put all of your eggs in one basket" is actually pretty sage advice.

> Paths into the network can open in an instant when a 0-day is discovered or disclosed.
>
> Previously friendly clients can turn hostile in an instant when a user becomes disgruntled.
>
> Phishing scams and malicious attachments constantly bombard email inboxes.

Thus, the need for "defense in depth" - there needs to be no single point of failure when it comes to cybersecurity.

Furthermore, governments, companies, and individuals that adopt a defense-in-depth mindset assume that, when it comes to cybersecurity attacks and breaches, it's sadly not a matter of "if" but "when". As countless hacks over the years have proven, given a sufficiently complex network, breaches of some type are inevitable. Thus, the question becomes, "What happens when an attacker breaches our defenses?" Do they immediately get the keys to the castle? Or do they find themselves faced with a whole new set of defenses to overcome?

Hopefully, it's the latter. We'll discuss some practical defense-in-depth strategies in next week's post.

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://www.grc.com/sn/SN-872-Notes.pdf](https://www.grc.com/sn/SN-872-Notes.pdf)
* [https://www.ghacks.net/2022/05/21/pwn2own-2022-windows-11-ubuntu-firefox-safari-tesla-and-more-hacked/](https://www.ghacks.net/2022/05/21/pwn2own-2022-windows-11-ubuntu-firefox-safari-tesla-and-more-hacked/)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏿‍💻 🌐 👨🏻‍💻
