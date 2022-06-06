# How to Publish the Weekly Cybersecurity Debrief

* NOTES:
  * Uses "John Smith" as an example name; replace with your name where needed.
  * Uses  "June 11, 2022" as the date of the debrief; replace with the date for your post where needed.

1. _Git_ yourself set up...in git.
    1. Clone the blog repo locally: [https://github.com/himaxwell/himaxwell.github.io](https://github.com/himaxwell/himaxwell.github.io)
    1. If you already have the repo locally, make sure you're up-to-date:  
    `git checkout master && git pull`
    1. Create a new branch for your post:  
    `git checkout -b jsmith/2022-06-11-security-debrief`

1. Create the file for your post.
    1. Things to note:
        1. Jekyll publishes the post on the date in the post's name; the file `_posts/3022-01-01-my-post.md` won't publish until January 1, 3022.
        1. Thus, even though the debrief covers say the week of June 05 (Sunday) - 11 (Saturday) 2022, if we want the post published on Friday, June 10, we will need to name the post accordingly.
    1. Create a new file under `_posts`, being sure to use the day you'd like the post to publish as the first part of the post's name. For a post that's for the week of June 05-11, 2022 that we want published on Friday, June 10, 2022, we would create the file:  
    `_posts/2022-06-10-cybersecurity-debrief-2022-06-11.md`.

1. Every day of the week, spend 15-20 minutes updating the post with content.
    1. NOTE: A few things to note re. writing your post:
        1. Jekyll does _not_ automatically parse links for you when compiling your pst. This is a bit surprising if you're used to links to straight URLs being automatically parsed for you.
            1. Thus, if you want to link to Google.com and have the link be clickable by your readers, you need to do:  
            `[https://google.com](https://google.com)`
            1. You can put any text you want in the square brackets and it will be rendered as the text that the user sees.
        1. There are a few ways to preview how your published post will look:
            1. The for this repo README mentions using the "_drafts" folder for writing/previewing your post. However, since your post is in the "_posts" folder, Jekyll should show your post no matter what if you run the Jekyll preview command in the REDME.
            1. Alternately, many code editors like Atom have a built-in markdown preview function, or you can probably add such functionality via a plugin.
    1. Update the "Major News Stories" section with the week's biggest cybersecurity stories. Some good outlets to keep an eye on:
        1. Listen to the daily "Internet Stormcast" from SANS: [https://isc.sans.edu/podcast.html](https://isc.sans.edu/podcast.html)
        1. Listen to the week's "Security Now" episode: [https://twit.tv/shows/security-now](https://twit.tv/shows/security-now)
        1. Keep an eye on Hacker News: [https://news.ycombinator.com](https://news.ycombinator.com)
    1. Update the "A few interesting deep-dive reads from the week" sub-section with any stories that are of interest but not necessarily headline-worthy.
    1. Update the "Other Software with Critical Patches Available" section with any major/well-known software that had an update during the week. Some ones to watch include:
        1. Zoom
        1. Browsers (Google Chrome, Mozilla Firefox, etc.)
        1. Any of the major operating systems (Windows, Mac, and Linux)
    1. Update the "Learning" section with 3-4 paragraphs on a cybersecurity topic of your choice.
        1. Please make sure this section is well-researched and has citations where needed/appropriate.

1. Publish the post on the Friday of the week being covered.
    1. Create a PR for your branch -> `master` in Github.
        1. *IMPORTANT*: Be sure that the base for your PR is `master` in the `himaxwell/himaxwell.github.io` repo.
            1. Because our repo was forked off of `barryclark/jekyll-now`, Github will automatically think you want to merge there!
            1. You don't! You want to merge to `master` in the `himaxwell/himaxwell.github.io` repo.
    1. Merge your PR with a commit message like:  
    `Add June 11, 2022 Cybersecurity Debrief #<PR Number Here>`
        1. Since these posts happen on a weekly basis, they've been approved for merging without PR review.
            1. Please do help us put our best foot forward by running a spell check on your post in Pages or something, just to catch any obvious spelling/grammar errors.
            1. Also, feel free to request review in the [#guild-eng-security Slack channel](https://app.slack.com/client/T040ZFA3W/C03HBUTJH4H) if you would like others to look over anything specific.
    1. The merge will kick off a Github action to rebuild and publish the site with your new post.
        1. Check the status of the build/publish action here: [https://github.com/himaxwell/himaxwell.github.io/actions](https://github.com/himaxwell/himaxwell.github.io/actions)
        1. Once the action completes, check the blog to make sure your post was published and looks great: [https://engineering.himaxwell.com](https://engineering.himaxwell.com)
    1. Post a message with the URL to your published post in the [#guild-eng-security Slack channel](https://app.slack.com/client/T040ZFA3W/C03HBUTJH4H).
