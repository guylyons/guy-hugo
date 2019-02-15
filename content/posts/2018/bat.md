---
title: "bat > cat"
date: 2018-09-19T20:22:14-04:00
updated: 2019-02-11
draft: false
tags: [shell, rust]
---
**bat** is a cat clone written completely from scratch in Rust and can be viewed as a successor to cat, that comes standard on all Linux distros, part of the
GNU core utils package.

https://www.gnu.org/software/coreutils/coreutils.html

From its man page:

    The cat utility reads files sequentially,
    writing them to the standard output.

<div class="note">For some **cat** basics and more: <a href="http://tldp.org/LDP/abs/html/basic.html">tldp.org/LDP/abs/html/basic.html</a>
</div>

And lately **bat** has become my go to command, offering some decent improvements over its predecessor, for peaking at files quickly when in the terminal.

An example of viewing this blog's config.toml file:

![bat in iTerm2](/posts/2018/term-bat.png)

It has Syntax highlighting, Git integration, and automatic paging, to name some features. I will typically pipe other commands thru bat for parsing, where I can get a nice, clean view of what the code or script would look like in my editor.

Take a look at sharkdp's GitHub page, try it out, and overall be a happier developer in your terminal:

https://github.com/sharkdp/bat
