---
layout: post
title: 'This Week in Cybersecurity: May 01-07, 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at the top cybersecurity stories from the week.
---

##  Major News Stories
* The drama of the [April 15 Heroku security incident](https://status.heroku.com/incidents/2413) continues.
  * Initally, details surrounding the incident were light; however, this week, Heroku posted the [following update](https://status.heroku.com/incidents/2413):
    > On April 7, 2022, a threat actor obtained access to a Heroku database and downloaded stored customer GitHub integration OAuth tokens. Access to the environment was gained by leveraging a compromised token for a Heroku machine account. According to GitHub, the threat actor began enumerating metadata about customer repositories with the downloaded OAuth tokens on April 8, 2022. On April 9, 2022, the attacker downloaded a subset of the Heroku private GitHub repositories from GitHub, containing some Heroku source code.  
    >
    > GitHub identified the activity on April 12, 2022, and notified Salesforce on April 13, 2022, at which time we began our investigation. As a result, on April 16, 2022, we revoked all GitHub integration OAuth tokens, preventing customers from deploying apps from GitHub through the Heroku Dashboard or via automation. We remain committed to ensuring the integration is secure before we re-enable this functionality.  
    >
    > Separately, our investigation also revealed that the same compromised token was leveraged to gain access to a database and exfiltrate the hashed and salted passwords for customers’ user accounts. For this reason, Salesforce is ensuring all Heroku user passwords are reset and potentially affected credentials are refreshed. We have rotated internal Heroku credentials and put additional detections in place. We are continuing to investigate the source of the token compromise.

  * As a result of the above disclosure, Heroku this week forced a password reset for all users.
* New work by US / Israeli security researches aims to demonstrate that Apple's M1 chipset may be vulnerable to Spectre-like data leakage.
  * Recall that Spectre is the name of a security vulnerability that exploits Intel processors' speculative execution pipeline. Initially designed to improve performance, in 2018 it came to light that speculative execution could be leveraged by an attacker to leak private information.
  * Researchers created [https://www.prefetchers.info](https://www.prefetchers.info/) to highlight similar concerns with Apple's new M1 chipset.
  * Currently, the attack is mostly conceptual and "not that bad", but it will be worth keeping an eye on in the coming months.
* A few interesting deep-dive reads from the week:
  * ["Fake Windows Updates Install Ransomware" (bleepingcomputer.com)](https://www.bleepingcomputer.com/news/security/fake-windows-10-updates-infect-you-with-magniber-ransomware/)
  * ["Botnet that hid for 18 months boasted some of the coolest tradecraft ever" (arstechnica.com)](https://arstechnica.com/information-technology/2022/05/how-hackers-used-smarts-and-a-novel-iot-botnet-to-plunder-email-for-months/)

## Other Software with Critical Patches Available
* [Zoom](https://explore.zoom.us/en/trust/security/security-bulletin/): Several patches for high-severity bugs landed this week.

## Learning -- Understanding CVEs

Next week, we'll start a deep-dive into a Rails CVE, but first it seems like we should answer the question - what exactly _is_ a "CVE"?

CVE stands for "Common Vulnerabilities and Exposures". It is a publicly-available list of unique identifiers for software vulnerabilities. The list was first published in September of 1999 and is managed by the [MITRE corporation](https://cve.mitre.org/).

When a software vulnerability is discovered and reported, it can be assigned a CVE identifier by a CVE Numbering Authority (CNA). Some well-known CNAs include Red Hat, IBM, Cisco, Oracle, and Microsoft.

CVEs are assigned a severity score using the Common Vulnerability Scoring System (CVSS), a set of open standards for assigning a number to a vulnerability to assess its severity. The CVSS uses a scale of 0.0 (least severe) to 10.0 (most severe). CVE entries are also given a CVE ID in the format `CVE-YYYY-<ID number here>`. For example, the first Ruby on Rails CVE was published in August of 2006 and was given the ID of `CVE-2006-4111`.

We'll take a look at `CVE-2006-4111` in more detail next time. In the meantime:
- The official CVE website is available here: [https://www.cve.org](https://www.cve.org)
- [https://www.cvedetails.com](https://www.cvedetails.com) is another great site that's worth a look. It has vulnerability feeds and widgets for various popular software products.

## Sources & Resources
The following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)](https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)
* [https://github.com/PagerDuty/security-training/blob/master/docs/for_engineers/index.md#prepared-statements](https://github.com/PagerDuty/security-training/blob/master/docs/for_engineers/index.md#prepared-statements)
* [https://www.redhat.com/en/topics/security/what-is-cve](https://www.redhat.com/en/topics/security/what-is-cve)
* [https://www.cve.org/About/History](https://www.cve.org/About/History)
* [https://www.cvedetails.com](https://www.cvedetails.com)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏼‍💻 🌐 🧑🏾‍💻
