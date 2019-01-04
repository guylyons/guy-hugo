---
title: "bat: an improvement on cat"
date: 2018-09-19T20:22:14-04:00
updated: 2018-09-29
draft: false
tags: [shell, rust]
---

cat is a tried and true program for concatenating and streaming output of files that comes standard on all *nix machines, and part of the
GNU core utils package.
https://www.gnu.org/software/coreutils/coreutils.html

So what's the big difference between bat and cat?

From its man page:

    The cat utility reads files sequentially,
    writing them to the standard output.

For some **cat** basics and more: http://tldp.org/LDP/abs/html/basic.html

But lately **bat** has become my go to command, and offers some decent improvements over its predecessor, for peaking at files quickly when in the terminal. It has Syntax highlighting, Git integration, and automatic paging, to name some features.

Take a look at sharkdp's GitHub page, try it out, and overall be a happier developer in your terminal:

https://github.com/sharkdp/bat