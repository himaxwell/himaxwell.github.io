---
layout: post
title: 'This Month in Cybersecurity: January 2023'
author_avatar: https://avatars.githubusercontent.com/u/2421172?v=4
author_name: Alex Smith
author_github_username: tradesmanhelix
excerpt: A look back at January 2023's top cybersecurity stories.
---

##  Major News Stories
#### Time to Say Goodbye

In 2023, we’ll say goodbye to a few more legacy technologies:

* [Verizon - the Last Major Carrier to Support 3G - Finally Pulls the Plug on the Venerable Technology](https://www.fiercewireless.com/wireless/verizon-tells-3g-customers-upgrade-they-lose-service): As the new year dawns, let’s pour one out for 3G’s years of faithful service. I have fond memories circa 2009 of seeing the 3G indicator on my iPhone 3G and smiling that I wouldn’t have to face the dial-up-like speeds of the Edge network.
* [Google Chrome Sunsetting support for Windows 7 / 8/8.1 in early 2023](https://support.google.com/chrome/thread/185534985/sunsetting-support-for-windows-7-8-8-1-in-early-2023?hl=en): You probably shouldn’t be going online using a Win 7/8 machine anyway...

#### Holiday Blues

Generally, the holidays are a quieter time of year cybersecurity-wise, but not 2022! This year saw...

##### _An Un-Merry Christmas..._
* [PyTorch Compromised](https://pytorch.org/blog/compromised-nightly-dependency/): The popular open-source machine learning framework for Python was compromised during the holiday, resulting in a malicious dependency package (`torchtriton`) being added to the Python Package Index (the official third-party software repo for Python ([source](https://en.wikipedia.org/wiki/Python_Package_Index))):

> Since the PyPI index takes precedence [over the PyTorch nightly package index, which contained the non-malicious version of torchtriton], this malicious package was being installed instead of the version from our official repository.  

* [Slack’s Private GitHub Code Stolen](https://www.bleepingcomputer.com/news/security/slacks-private-github-code-repositories-stolen-over-holidays/): In the “oh I fogot Salesforce owned them too” category, BleepingComputer writes about how some of Slack's source code was compromised over the holidays:

> The incident involves threat actors gaining access to Slack’s externally hosted GitHub repositories via a 'limited' number of Slack employee tokens that were stolen.
> 
> While some of Slack's private code repositories were breached, Slack’s primary codebase and customer data remain unaffected, according to the company.

##### _...And a Very Leaky New Year_
* [CircleCI kicks off the new year by asking customers to rotate any secrets stored on the CircleCI platform](https://circleci.com/blog/january-4-2023-security-alert/)
* [Twitter’s strugles continue into 2023 as attackers release 200 million Twitter user email addresses that were originally stolen back in 2021](https://www.bleepingcomputer.com/news/security/200-million-twitter-users-email-addresses-allegedly-leaked-online/)


#### LastPass Fallout

Steve Gibson, cybersecurity expert and co-host of the popular “Security Now” podcast, has dedicated two of his January podcast episodes to discussing the fallout from the most-recent LastPass breach and why he’s now moved on from his long-time password manager of choice (Steve has been a LastPass user since about day 1). These episodes are a great resource for anyone wanting a bit more context around the situation or advice on where to go from here:
* [SECURITY NOW 904 - LEAVING LASTPASS](https://twit.tv/shows/security-now/episodes/904?autostart=false)
* [SECURITY NOW 905 - 1](https://twit.tv/shows/security-now/episodes/905?autostart=false)

Frighteningly, it’s been discovered that, for some LastPass users, their vault was set to use 1 iteration when encrypting the vault with PBKDF2, which means, “200 GPUs could crack [a] 40-bit entropy password in an average of 61.56 seconds.” (See the second episode above.)

Sadly, this situation only continues to get worse as more information comes to light: [https://old.reddit.com/r/sysadmin/comments/10kp4ye/lastpass_breach_gets_worse/](https://old.reddit.com/r/sysadmin/comments/10kp4ye/lastpass_breach_gets_worse/)

#### ReVoLTE Attack: Eavesdropping Encrypted LTE Calls

The site https://revolte-attack.net details an interesting new attack: “We introduce ReVoLTE, an attack that exploits an LTE implementation flaw to recover the contents of an encrypted VoLTE call. This enables an adversary to eavesdrop on VoLTE phone calls. ReVoLTE makes use of a predictable keystream reuse, which was discovered by Raza & Lu. Eventually, the keystream reuse allows an adversary to decrypt a recorded call with minimal resources.”

You can test whether or not your carrier is vulnerable using their app: https://revolte-attack.net/#app. “The App requires a VoLTE capable Android phone with root access and a Qualcomm chipset.”

#### New Git security Vulnerabilities Announced

On its blog, [Github writes](https://github.blog/2023-01-17-git-security-vulnerabilities-announced-2/) about several new vulnerabilities discovered in Git:

> Git users are encouraged to upgrade to the latest version, especially if they use `git archive`, work in untrusted repositories, or use Git GUI on Windows.

Interestingly, several of the CVE’s were discovered by employees of Github rival Gitlab.

Git version `2.39.1` fixes these issues and is available for download now.

#### Patch your Ryzen and EPYC systems

[Tom’s Hardware reports](https://www.tomshardware.com/news/amd-discloses-31-new-cpu-vulnerabilities) that AMD has disclosed 31 new vulnerabilities in its CPUs. The bugs affect  its Ryzen and EPYC processors and range in severity from “high” to “low.”

Interestingly, AMD seems keen to keep these vulnerabilities out of the limelight. From the above Tom’s Hardware article:

> AMD didn’t announce the vulnerabilities with a press release or other outreach — it merely posted the lists — so we’re working to tease out the details and will update when we have more information.

Some affected processors have yet to receive any mitigations and the performance impact of the fixes is not yet clear, so it will be interesting to see how this story develops given AMD’s image as the more-secure alternative to Intel, an image Tom’s Hardware notes might not be fully warranted:

> AMD’s chips have long been known for having fewer known vulnerabilities than Intel’s models. However, it’s hard to ascertain if the initially limited discoveries in AMD processors were due to a security-first approach to hardened processor design, or if researchers and attackers merely focused on Intel’s processors due to their commanding market share: Attackers almost always focus on the broadest cross-section possible.

#### Monkey See, Monkey Sudoedit:

Synacktive [has posted a great write-up](https://www.synacktiv.com/sites/default/files/2023-01/sudo-CVE-2023-22809.pdf) on a vulnerability they found in the `sudo` (super user do) command when using `sudoedit`.

An excellent deep-dive on the `sudoedit` command is available [here](https://www.howtoforge.com/tutorial/how-to-let-users-securely-edit-files-using-sudoedit/), but in short:

> Sudoedit is a built-in command that allows users to securely edit files. According to the sudo man page, ‘sudoedit’ is equivalent to executing ‘sudo’ with the ‘-e’ command line option.

A summary of the vulnerability reads:

> Sudo uses user-provided environment variables to let its users select their editor of choice. The content of these variables extends the actual command passed to the sudo_edit() function. However, the latter relies on the presence of the -- argument to determine the list of files to edit. The injection of an extra -- argument in one of the authorized environment variables can alter this list and lead to privilege escalation by editing any other file with privileges of the RunAs user. This issue occurs after the sudoers policy validation.

Once again, pwned by the text editor!

## Other Software with Critical Patches Available
* Apple released a slew of updates this month, including iOS 16.3: [https://isc.sans.edu/forums/diary/Apple%20Updates%20%28almost%29%20Everything%3A%20Patch%20Overview/29472/](https://isc.sans.edu/forums/diary/Apple%20Updates%20%28almost%29%20Everything%3A%20Patch%20Overview/29472/)
* Microsoft January 2023 Patch Tuesday: “In the first Patch Tuesday of 2023, we got patches for 98 vulnerabilities. Of these, 11 are critical, 1 was previously disclosed, and 1 is already being exploited, according to Microsoft.” [source](https://isc.sans.edu/diary/Microsoft%20January%202023%20Patch%20Tuesday/29420)
* [Zoom for MS Windows Patches High-Severity CVE](https://explore.zoom.us/en/trust/security/security-bulletin/)

## Deep Dives
A few interesting deep-dive reads from the month:
* [FanDuel Discloses Data Breach Caused by Recent Mailchimp Hack](https://www.bleepingcomputer.com/news/security/fanduel-discloses-data-breach-caused-by-recent-mailchimp-hack/)
* [OneNote Documents Used to Embed Malicious Office Documents](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/trojanized-onenote-document-leads-to-formbook-malware/)

## Learning -- `CVE-2008-4094`

First disclosed on Tuesday, September 30, 2008 and earning itself a CVE score of 7.5/10, `CVE-2008-4094` was a SQL-injection vulnerability that affected all things `Action`:

> Multiple SQL injection vulnerabilities in Ruby on Rails before 2.1.1 allow remote attackers to execute arbitrary SQL commands via the (1) :limit and (2) :offset parameters, related to ActiveRecord, ActiveSupport, ActiveResource, ActionPack, and ActionMailer.
> 
> ([source](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-4094))

At the time, the "Rails Security Project" published a [great write-up on the vulnerability](https://rorsecurity.info/journal/2008/09/08/sql-injection-issue-in-limit-and-offset-parameter.html). In it, they explain how the issue could be exploited via queries such as:

```sql
Person.find(:all, :limit => “10; DROP TABLE users;”)
```

A look at the [Git diff between Rails 2.1.0 and 2.1.1](https://github.com/rails/rails/compare/v2.1.0...v2.1.1) shows that the fix came in commit [4d850e43d751bff95e25bcd36f7d660ba1d43f2a](https://github.com/rails/rails/commit/4d850e43d751bff95e25bcd36f7d660ba1d43f2a) and was relatively simple (a `+` at the beginning of a line means new code that was added; `-` is old code that was removed):

```ruby

      def add_limit_offset!(sql, options) #:nodoc:
        if limit = options[:limit]
+         limit = sanitize_limit(limit)
          unless offset = options[:offset]
            sql << " LIMIT #{limit}"
          else
-           sql << " LIMIT #{offset}, #{limit}"
+           sql << " LIMIT #{offset.to_i}, #{limit}"
          end
        end
      end
```

First off, if a `limit` is passed, the code now sanitizes it before use. Second, if present, the code explicitely casts the `offset` to an integer, which is all it ever should be anyway.

The improved code above is a great example of defensive programming that treats user-supplied input as unsafe by default and sanitizes it before use.

## Sources & Resources
In addition to inline citations, the following were used or referenced when preparing this debrief.
* [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
* [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)

----

Thanks for reading, stay safe out there, and have a great weekend! 👩🏽‍💻 🌐 👨🏼‍💻
