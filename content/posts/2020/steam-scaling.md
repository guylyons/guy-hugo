---
title: "Steam Scaling in Linux Gnome"
date: 2020-11-04T08:25:54-05:00
draft: true
---

If you have a high resolution monitor or panel on your laptop and are using 200% scaling, some applications might not render the way you'd expect. In this case,
we're talking about Steam.

The fix for this is relatively simple, which is to simply add the enviornment
variable:

    env GDK_SCALE=2

A better way to set this is by copying the 

https://wiki.archlinux.org/index.php/Desktop_entries

Explain here

    cp /usr/share/applications/steam.desktop ~/.local/share/applications/

Explain here

    Exec=env GDK_SCALE=2 /usr/bin/steam %U


