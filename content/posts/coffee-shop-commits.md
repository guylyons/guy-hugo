---
title: "Coffee Shop Commits"
date: 2018-10-01T11:06:54-04:00
draft: false
tags: ["shell", "git"]
---

## The scenario

You sit down to your favorite coffee shop, take in an aromatic sip of your conflict free, freshly purchased (albeit overpriced) cup of joe, and ready your commit message to push up to your repo. Then, seemingly out of nowhere, you're hit with this:

```
❯ git push origin master
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

## WHAT-THE-ACTUAL-F*** 

Ok, take a deep breath.

What's may have happened (at least in my case) is port 22 is being blocked by the server. Word to the wise and newly informed: save yourself some time and frustration, and don't go running for the ssh-keygen just yet. I just did this this morning, annoyed and frustrated until I finally realised what was going on.

But before doing anything, let's run some simple tests.

```
ssh -T git@github.com
```

Use this to test the connection and ensure that you're actually able to connect or not. This will save you a lot of time instead of needlessly trying to push up to master over and over.

You can also run this with the -v flag for added verbosity.

## The Exhale 

If chances are pretty good that port 22 is being blocked, you may want to find a new shop to frequent. It's likely they're doing this for the very purpose of keeping coders out of their shops all day long, who only drink one cup of coffee and chill for the day. Be that as it may, there ares till ways around this.

This thread from StackExchange offers some good insight and options:
https://unix.stackexchange.com/questions/253591/ssh-into-a-remote-server-but-my-organization-has-blocked-port-22