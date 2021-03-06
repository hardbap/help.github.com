---
layout: default
title: Common issues and questions
description: Solutions to the most common issues and answers to common questions
categories: troubleshooting popular
---

I can't push, "Permission denied (publickey)"
---------------------------------------------

Make sure you've [set up an SSH key](/key-setup-redirect) and are using the correct URL (they are case-sensitive).  Check [this guide](/troubleshooting-ssh) for more information.

My commits aren't linked to my user, to the wrong user, or don't have a Gravatar
-----------------------------------------------------------------------------------

Make sure your [git](/git-email-settings) and [GitHub](https://github.com/settings/emails) email settings match.

You may also need to check your Gravatar account to make sure your Gravatar has a "G" rating.

I changed my Gravatar but it's not updating
-------------------------------------------

Gravatar images are cached for a very long time. Clear your browser's cache.

Syntax highlighting isn't working for my language
-------------------------------------------------

We use the excellent [pygments](http://pygments.org/) library for our syntax highlighting. Check their list of [supported languages](http://pygments.org/languages/) and learn how to specify a lexer for yours. If you contribute a lexer back to pygments, let us know and we’ll make sure it’s made available here on GitHub.

Can I use Eclipse/EGit with GitHub?
-----------------------------------

Yes, see [the EGit user guide](http://wiki.eclipse.org/EGit/User_Guide) for help.

Are there any screencasts or other resources out there for git?
---------------------------------------------------------------

Yes, you can find a *(probably incomplete)* list [here](http://gist.github.com/423320).
