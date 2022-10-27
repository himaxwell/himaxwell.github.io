---
layout: post
title: 'This Month in Cybersecurity: October 2022'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at October 2022's top cybersecurity stories.
---

##  Major News Stories
#### PSA: Get Ready to Patch all the (OpenSSL) Things
This just in [from SANS](https://isc.sans.edu/diary/rss/29192): "OpenSSL announced that they will release OpenSSL 3.0.7 this coming Tuesday [November 1, 2022]. It will fix a critical vulnerability [1]. The OpenSSL definition of critical: ... 'Vulnerabilities which can be easily exploited remotely to compromise server private keys or where remote code execution is considered likely in common situations.' ...In short: This is something you will need to worry about!"

Since OpenSSL is widely deployed and tends to be one of those things that organizations can easily be using without even realizing it, it looks like we may be in store for a bumpy November when it comes to cybersecurity.

#### PSA: TikTok Can Track You Across the Web, Even If You Don’t Use the App
Consumer Reports [released a study](https://www.consumerreports.org/electronics-computers/privacy/tiktok-tracks-you-across-the-web-even-if-you-dont-use-app-a4383537813/) detailing how TikTok is the latest big tech company to track people across the web, no TikTok account required. The technology used is similar to that of [Facebook's notorious tracking pixel](https://www.consumerreports.org/privacy/how-facebook-tracks-you-even-when-youre-not-on-facebook-a7977954071/). CR recommends that concerned users take steps to protect their personal information by using a privacy-protecting browser extension like uBlock Origin and either locking down their browser's privacy settings or using a privacy-respecting browser like Firefox, Vivaldi, or Brave.

#### Microsoft's Bad Month
Early October saw several CVE's discovered in Microsoft's popular Exchange email server. Microsoft [recommended remediating exploitation via a URL-rewrite rule](https://microsoft.github.io/CSS-Exchange/Security/EOMTv2/), only for significant flaws to be discovered in that rule one day later. @testanull [tweeted](https://twitter.com/testanull/status/1576774007826718720), "Lol The URL pattern to detect/prevent the Exchange 0day provided in MSRC's blog post can easily be bypassed." Microsoft [responded](https://msrc-blog.microsoft.com/2022/09/29/customer-guidance-for-reported-zero-day-vulnerabilities-in-microsoft-exchange-server/) releasing updated versions of the URL rewrite rule each day on October 4-8 (five days in a row). By mid October, [flaws were still being found](https://twitter.com/wdormann/status/1581631889252569089) in Microsoft's rewrite rule.

Mid-October also saw Ars Technica release an [article](https://arstechnica.com/information-technology/2022/10/how-a-microsoft-blunder-opened-millions-of-pcs-to-potent-malware-attacks/) titled, “How a Microsoft blunder opened millions of PCs to potent malware attacks.” In a nutshell, Windows purports to maintain a list of potentially dangerous drivers whose installation it should block, except the list hadn’t been updated since 2019, so users with this protection enabled were given a false sense of security.

Finally, security researchers have discovered a flaw with Office 365. An [article](https://labs.withsecure.com/advisories/microsoft-office-365-message-encryption-insecure-mode-of-operation) from W/Labs entitled, “Microsoft Office 365 Message Encryption Insecure Mode of Operation” details how Office 365 Message Encryption (OME) uses an insecure encryption mode which can leak part or all of the encrypted message.

Interestingly, all of the above share something in common - Microsoft’s disappointing response:
* The recommended Exchange filter has been fumbled multiple times and (as of this writing) does not fully protect from attackers,
* Microsoft has yet to commit to a plan for keeping its driver blocklist updated, surprising for a feature that has been advertised as something users can rely on for protection (they can’t - the list is too outdated to do much good), and
* Microsoft has stated that they will not address the insecure encryption mode in Office 365 Message Encryption: “The report was not considered meeting the bar for security servicing, nor is it considered a breach. No code change was made and so no CVE was issued for this report.”

One can only wonder what is going on over there in Redmond. Hopefully it turns out that the real security team is just taking October off and some temps have been the ones manning Microsoft’s security response channels this month.

#### A CVE Old Enough to Drink
On October 25, Trail of Bits [disclosed CVE-2022-35737](https://blog.trailofbits.com/2022/10/25/sqlite-vulnerability-july-2022-library-api/), a vulnerability which was, "Introduced in SQLite version 1.0.12 (released on October 17, 2000) and fixed in release 3.39.2 (released on July 21, 2022)." Sad timing for this CVE - having attained the legal drinking age in the USA last year, it was planning on graduating from college this coming spring and doing some traveling before starting an internship with a leading tech company.

All joking aside, Trail of Bits has given this vulnerability the awesome name of "Stranger Strings" and [summarizes it with](https://blog.trailofbits.com/2022/10/25/sqlite-vulnerability-july-2022-library-api/), "On vulnerable systems, CVE-2022-35737 is exploitable when large string inputs are passed to the SQLite implementations of the printf functions and when the format string contains the %Q, %q, or %w format substitution types. This is enough to cause the program to crash. We also show that if the format string contains the ! special character to enable unicode character scanning, then it is possible to achieve arbitrary code execution in the worst case, or to cause the program to hang and loop (nearly) indefinitely."

## Other Software with Critical Patches Available
* [Apple Patches Everything: October 2022 Edition](https://isc.sans.edu/forums/diary/Apple+Patches+Everything+October+2022+Edition/29182).

## Deep Dives
A few interesting deep-dive reads from the month:
* [What is in your Infosec Calendar?](https://isc.sans.edu/forums/diary/What+is+in+your+Infosec+Calendar/29118)
* [Fully Undetectable Powershell Backdoor](https://www.safebreach.com/resources/blog/safebreach-labs-researchers-uncover-new-fully-undetectable-powershell-backdoor/)
* [Exploited Windows Zero Day Lets JavaScript Files Bypass Security Warnings](https://www.bleepingcomputer.com/news/security/exploited-windows-zero-day-lets-javascript-files-bypass-security-warnings/)

## Learning -- `CVE-2007-5380`
First recorded on October 19, 2007 and earning itself a CVE score of 6.8 out of 10, the description for `CVE-2007-5380` reads, "Partial	Session fixation vulnerability in Rails before 1.2.4, as used for Ruby on Rails, allows remote attackers to hijack web sessions via unspecified vectors related to 'URL-based sessions.'"

More helpfully, the [Rails blog post](https://rubyonrails.org/2007/10/5/rails-1-2-4-maintenance-release) for the 1.2.4 update states, "Session fixation attacks are mitigated by removing support for URL-based sessions." This of course begs the question, "What are URL-based sessions? What is session fixation?"

[Wikipedia](https://en.wikipedia.org/wiki/Session_fixation) gives this simple example of session fixation:

> Alice has an account at the bank `http://unsafe.example.com/`.
>
> Mallory intends to target Alice's money from her bank.
>
> Alice has a reasonable level of trust in Mallory, and will visit links Mallory sends her.
>
> Mallory has determined that `http://unsafe.example.com/` accepts any session identifier, accepts session identifiers from query strings and has no security validation. `http://unsafe.example.com/` is thus not secure.
>
> Mallory sends Alice an e-mail: "Hey, check this out, there is a cool new account summary feature on our bank, `http://unsafe.example.com/?SID=I_WILL_KNOW_THE_SID`". Mallory is trying to fixate the SID [session ID] to `I_WILL_KNOW_THE_SID`.
>
> Alice is interested and visits `http://unsafe.example.com/?SID=I_WILL_KNOW_THE_SID`. The usual log-on screen pops up, and Alice logs on.
>
> Mallory visits `http://unsafe.example.com/?SID=I_WILL_KNOW_THE_SID` and now has unlimited access to Alice's account.

The above is the simplest form of session fixation attack. Other, more sophisticated versions exist, including ones that exploit server-generated session IDs, but the gist of the issue is that URL-based sessions are a minefield. It's very difficult to do them correctly and better session mechanisms (such as cookies) already exist, so there's no reason to use URL-based sessions.

Apparently, the Rails team felt the same way. Once CVE-2007-5380 was disclosed, they yanked support for URL-based sessions out of Rails entirely, thereby eliminating this attack vector entirely. Given that we are 15+ years down the road from this decision, one can only imagine how many applications were steered away from using an insecure technology simply because they couldn't. Thank you Rails team!

For more information on secure session management, check out this OWASP cheat sheet: [https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html)

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)
* [https://security.stackexchange.com/questions/14093/why-is-passing-the-session-id-as-url-parameter-insecure](https://security.stackexchange.com/questions/14093/why-is-passing-the-session-id-as-url-parameter-insecure)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏻‍💻 🌐 👨🏿‍💻
