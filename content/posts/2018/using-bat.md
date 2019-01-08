---
title: "Using bat"
date: 2018-09-19T20:22:14-04:00
updated: 2018-09-29
draft: false
tags: [shell, rust]
---
bat is written from scratch and can be looked at as a successor to the cat program that comes standard on all unix/linux systems.

Most everyone should be familiar with **cat**, a tried and true program for concatenating and streaming output of files that comes standard on all *nix machines, and part of the
GNU core utils package.

https://www.gnu.org/software/coreutils/coreutils.html

From its man page:

    The cat utility reads files sequentially,
    writing them to the standard output.

<div class="note">For some **cat** basics and more: http://tldp.org/LDP/abs/html/basic.html
</div>

But lately **bat** has become my go to command, and offers some decent improvements over its predecessor, for peaking at files quickly when in the terminal. It has Syntax highlighting, Git integration, and automatic paging, to name some features.

Take a look at sharkdp's GitHub page, try it out, and overall be a happier developer in your terminal:

https://github.com/sharkdp/bat