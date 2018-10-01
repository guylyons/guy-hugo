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

```
ssh -vT git@github.com
```

Use this to test the connection and ensure that you're actually able to connect or not. This will save you a lot of time instead of needlessly trying to push up to master over and over.

### Trying Another Web Host 

This could help, and if it's isolated to one provider than another, then you've found your problem.

But it's also worth noting that the error message you get back will vary depending what you use to host your repositories. BitBucket will return something slightly different. This is what I received back after trying this out:

```
Connection closed by xx.xxx.xx.x port 22
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

It was around this point I realized port 22 was being blocked.

## The Exhale 

If you've exhausted trying to connect and it seems port 22 is being blocked, you may want to find a new shop to frequent. It's likely they're doing this for the very purpose of keeping coders out of their shops all day long, who only drink one cup of coffee and chill for the day. Be that as it may, there ares till ways around this.

This thread from StackExchange offers some good insight and options:
https://unix.stackexchange.com/questions/253591/ssh-into-a-remote-server-but-my-organization-has-blocked-port-22

### Resources
- https://help.github.com/articles/connecting-to-github-with-ssh/
- https://help.github.com/categories/authenticating-to-github/
- https://help.github.com/articles/error-permission-denied-publickey/