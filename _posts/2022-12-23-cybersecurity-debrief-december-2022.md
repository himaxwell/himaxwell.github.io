---
layout: post
title: 'This Month in Cybersecurity: December 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at December 2022's top cybersecurity stories.
---

##  Major News Stories
#### The Last Straw for LastPass?
For possibilities under the heading, "Things you never want to hear from your password manager," "they now have your vault" is probably top of the list for most of us. Sadly, for LastPass users, this is exactly what has happened.

On its blog, [the company writes](https://blog.lastpass.com/2022/12/notice-of-recent-security-incident/), "We recently notified you that an unauthorized party gained access to a third-party cloud-based storage service, which LastPass uses to store archived backups of our production data...The threat actor may attempt to use brute force to guess your master password and decrypt the copies of vault data they took."

Given that computers only get faster and that the encryption of the stolen vaults is only as good as the master password used to encrypt it, this is a very concerning development and LastPass customers should definitely reset any of the passwords they had stored in LastPass.

#### Spy Cameras
MacRumors reports that [Anker’s Eufy Cameras have been caught uploading content to the cloud without user consent](https://www.macrumors.com/2022/11/29/eufy-camera-cloud-uploads-no-user-consent/). The company responded, blaming the issue on push notifications of all things:

> To provide users with push notifications to their mobile devices, some of our security solutions create small preview images (thumbnails) of videos that are briefly and securely hosted on an AWS-based cloud server. These thumbnails utilize server-side encryption and are set to automatically delete and are in compliance with Apple Push Notification service and Firebase Cloud Messaging standards. Users can only access or share these thumbnails after securely logging into their eufy Security account.
>
> Although our eufy Security app allows users to choose between text-based or thumbnail-based push notifications, it was not made clear that choosing thumbnail-based notifications would require preview images to be briefly hosted in the cloud.

#### Microsoft Updates
In [Microsoft’s December 2022 Patch Tuesday](https://isc.sans.edu/diary/Microsoft%20December%202022%20Patch%20Tuesday/29336), “We got patches for 74 vulnerabilities. Of these, 7 are critical, 1 was previously disclosed, and 1 is already being exploited, according to Microsoft.” As is becoming the norm, there were a few post-release woes:
* [Known issues in this update](https://support.microsoft.com/en-us/topic/december-13-2022-kb5021249-os-build-20348-1366-d5fe7608-bc9d-4055-a88c-fb2fd3d5fd45)
* [So, you say your DC’s memory is getting all used up](https://techcommunity.microsoft.com/t5/ask-the-directory-services-team/so-you-say-your-dc-s-memory-is-getting-all-used-up-after/ba-p/3696318)

This month, Microsoft also [announced the EOL date for the last version of Internet Explorer](https://learn.microsoft.com/en-us/deployedge/edge-learnmore-neededge): "The retired, out-of-support Internet Explorer 11 desktop application is scheduled to be permanently disabled through a Microsoft Edge update on certain versions of Windows 10 on February 14, 2023." For most of us, this will definitely be one of those funerals that has more of a party feel to it.

#### Good for You Github
Github made a few moves this month to improve the security of its platform:
* “GitHub will require all users who contribute code on GitHub.com to enable one or more forms of two-factor authentication (2FA) by the end of 2023.” [source](https://github.blog/2022-12-14-raising-the-bar-for-software-security-next-steps-for-github-com-2fa/)
* “Secret scanning is now available for free on public repositories.” [source](https://github.blog/changelog/2022-12-15-secret-scanning-is-now-available-for-free-on-public-repositories/)

#### Visual Studio PWN
Google [recently disclosed](https://github.com/google/security-research/security/advisories/GHSA-pw56-c55x-cm9m) a remote code execution vulnerability in the popular Visual Studio Code editor:

> An attacker could, through a link or website, take over the computer of a Visual Studio Code user and any computers they were connected to via the Visual Studio Code Remote Development feature. This issue affected at least GitHub Codespaces, github.dev, the web-based Visual Studio Code for Web and to a lesser extent Visual Studio Code desktop.

The issue was first reported back in August, fixed in October, and publicly disclosed on November 22. Great reminder to keep your software updated as, these days, even something as seemingly benign as a text editor can be used to pwn your computer!

## Other Software with Critical Patches Available
* Apple released a slew of updates this month, including iOS 16.2: [https://isc.sans.edu/diary/Apple%20Updates%20Everything/29338](https://isc.sans.edu/diary/Apple%20Updates%20Everything/29338)

## Deep Dives
A few interesting deep-dive reads from the month:
* [NIST Retires SHA-1 Cryptographic Algorithm](https://www.nist.gov/news-events/news/2022/12/nist-retires-sha-1-cryptographic-algorithm)
* [Google says Google should do a better job of patching Android phones](https://arstechnica.com/gadgets/2022/11/google-says-google-should-do-a-better-job-of-patching-android-phones/)
* [Stolen Android Keys used to Sign Info-Stealing Malware](https://www.theregister.com/2022/12/05/compromised_android_keys/)

## Learning -- Cybersecurity Predictions for 2023
The end of the year is always a great time to reflect on the past year and plan for the one ahead. Looking forward to 2023, here are a few cybersecurity predictions:

1. **Updates will continue to be critical but hard**. Updates are how software vendors protect their users from the latest threats, but this turns into a catch 22 when the updates themselves often introduce new bugs or cause issues. No company has completely solved this, but it's the ideal our industry needs to continue to chase. Will 2023 see the user experience around software updates improve or worsen? Probably the latter.

2. **Memory-safe languages will make attackers' lives more difficult**. The Rust programming language continues to see increased adoption, now shipping in both the Linux kernel and in Android. As more and more code becomes memory safe, we will continue to see a decrease in memory-related hacks and flaws. This is good but also means...

3. **Phishing will take on an even more prominent role in attackers' bag of tricks**. As it becomes more difficult to trip up machines, attackers will continue to focus on the weakest link - human beings. 2023 will likely see an even greater number of phishing attacks used as the means of compromising victims.

Hopefully 2023 will also see an increase in cybersecurity education and awareness. As technology becomes a bigger and bigger part of modern life, the demand and interest in the field will only grow, bringing with it a lot of opportunity and (probably) crazy headlines.

And we'll be here to discuss them with you - see you in 2023!

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏾‍💻 🌐 👨🏻‍💻
