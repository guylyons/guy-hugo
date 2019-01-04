---
title: "Setting your Paths in Emacs"
date: 2018-09-30T22:47:10-04:00
draft: false 
tags: ["emacs"]
---
Being able to run your ever day terminal commands in Emacs is really handy, but if you haven't configured your PATH, you probably don't have access to them.

Sometimes I see demos on YouTube where the person is window hopping from Emacs to iTerm2 -- all because they're unable to access a path their Bash or Zsh in iTerm2 already has access to.

But you don't need to window hop. So similar to the $PATH variable in Bash, in Emacs you'll need to set your 'exec-path' and your "PATH" via setenv.

To set paths up correctly in Emacs looks something like this:

```
;; required for exposing commands in eshell or sane term. 
;; Similar to setting your $PATH in BASH
(setenv "PATH" (concat (getenv "PATH") ":/usr/local/bin"))

;; exec-path is used for Emacs programs that need to execute binaries. E.g.: ag, npm
(setq exec-path (append exec-path '("/usr/local/bin")))
```

Place the above in your init.el file.

For my personal workflow and habits, this allows me to minmize window hopping, and keep more of my work in Emacs, which is always a good thing.

### Resources

https://www.emacswiki.org/emacs/ExecPath