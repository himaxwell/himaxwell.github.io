---
layout: post
title: 'This Week in Cybersecurity: May 08-14, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---

##  Major News Stories
* This week, F5's BIG-IP network appliances (software and/or hardware devices used for proxying, load balancing, etc.) gave a good reminder of why it's always good to ensure that device management interfaces aren't exposed to the public internet: CVE-2022-1388 allowed an unauthenticated attacker to run code on the devices. Several honeypots reported seeing attempts at running `rm -rf /*`, aka. erase the entire file system!
* Also this week, Rubygems.org released a security advisory for CVE-2022-29176: "The advisory was about a bug, which allowed a malicious user to yank certain gems, and to upload different files with the same name, same version number, and different platform." More information and a nice succinct break down of the issue [here](https://greg.molnar.io/blog/rubygems-cve-2022-29176/).
* A few interesting deep-dive reads from the week:
  * [What is the simplest malware in the world?](https://isc.sans.edu/forums/diary/What+is+the+simplest+malware+in+the+world/28620/)
  * [npm "foreach" package domain takeover](https://www.theregister.com/2022/05/10/security_npm_email/); [the attack may have been part of a pen test?](https://jfrog.com/blog/npm-supply-chain-attack-targets-german-based-companies/)


## Other Software with Critical Patches Available
* Microsoft's May 2022 patch Tuesday was this week. Some pretty important patches landed for actively-exploited 0-days, so patch your Windows systems ASAP.

## Learning -- `CVE-2006-4111`
Ruby on Rails first CVE was `CVE-2006-4111`, publicly disclosed on Monday, August 14, 2006.

Earning itself a CVSS score of 7.5/10, the vulnerability affected Rails versions < 1.1.5 and allowed, "remote attackers to execute Ruby code with 'severe' or 'serious' impact via a File Upload request with an HTTP header that modifies the LOAD_PATH variable." [1]

In Ruby, the `LOAD_PATH` variable is used to tell Ruby where to look for files: "The [Ruby] `require` keyword searches for the dependencies in the array [set by] `$LOAD_PATH` and tries to load it for the file that has a dependency on [a] certain library." [2]

Thus, this CVE allowed attackers to modify the locations Ruby searches for executable scripts via a simple file upload. Bonus points to any attackers who figured out how to get Ruby to execute their uploaded file by adding the file uploads directory to the `LOAD_PATH` - yikes!

[1] [https://www.cvedetails.com/cve/CVE-2006-4111](https://www.cvedetails.com/cve/CVE-2006-4111/)  
[2] [https://medium.com/@aayushsharda/why-to-use-load-path-in-ruby-ce971bc1d864](https://medium.com/@aayushsharda/why-to-use-load-path-in-ruby-ce971bc1d864)  
[3] [There's also a fun historical write-up with a code diff here](https://web.archive.org/web/20060819084829/http://blog.koehntopp.de/archives/1367-Ruby-On-Rails-Mandatory-Mystery-Patch.html)

## Sources & Resources
The following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://www.bleepingcomputer.com/news/security/critical-f5-big-ip-vulnerability-exploited-to-wipe-devices/](https://www.bleepingcomputer.com/news/security/critical-f5-big-ip-vulnerability-exploited-to-wipe-devices/)
* [https://www.appdeliveryworks.com/BIG-IP-Software.asp](https://www.appdeliveryworks.com/BIG-IP-Software.asp)
* [https://isc.sans.edu/forums/diary/F5+BIGIP+Unauthenticated+RCE+Vulnerability+CVE20221388/28624/](https://isc.sans.edu/forums/diary/F5+BIGIP+Unauthenticated+RCE+Vulnerability+CVE20221388/28624/)
* [https://github.com/horizon3ai/CVE-2022-1388](https://github.com/horizon3ai/CVE-2022-1388)
* [https://greg.molnar.io/blog/rubygems-cve-2022-29176/](https://greg.molnar.io/blog/rubygems-cve-2022-29176/)
* [https://isc.sans.edu/forums/diary/Microsoft+May+2022+Patch+Tuesday/28632/](https://isc.sans.edu/forums/diary/Microsoft+May+2022+Patch+Tuesday/28632/)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏽‍💻 🌐 🧑🏽‍💻
