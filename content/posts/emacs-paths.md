---
title: "Setting your Paths in Emacs"
date: 2018-09-30T22:47:10-04:00
draft: false 
tags: ["emacs"]
---
Being able to run commands in Emacs that you use everyday in your regular terminal is really handy. Sometimes I'll see people on YouTube window hopping from Emacs to iTerm2 or the like, all because they're unable to access a path that clearly their Bash or Zsh in iTerm2 already has access to.

So similar to the $PATH variable in Bash, in Emacs you'll need to set your 'exec-path'

Setting your paths up correctly in Emacs looks something like, and will go in your init.el:

```
;; required for exposing commands in eshell or sane term, for instance.
;; Similar to setting your $PATH in BASH
(setenv "PATH" (concat (getenv "PATH") ":/usr/local/bin"))

;; exec-path is used for Emacs programs that need to execute binaries. E.g.: ag, npm
(setq exec-path (append exec-path '("/usr/local/bin")))
```

For my personal workflow and habits, this allows me to minmize window hopping, and keep more of my work in Emacs.