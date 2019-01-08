---
title: "Setting your Paths in Emacs"
date: 2018-09-30T22:47:10-04:00
draft: false 
tags: ["emacs"]
---

Being able to run your everyday terminal commands in Emacs is really handy, but if you haven't configured your PATH, you probably don't have access to them.

Similar to the $PATH variable in Bash, in Emacs you'll need to set your 'exec-path' and your "PATH" via setenv.

{{< highlight lisp >}}
;; required for exposing commands in eshell or sane term. 
;; Similar to setting your $PATH in BASH
(setenv "PATH" (concat (getenv "PATH") ":/usr/local/bin"))

;; exec-path is used for Emacs programs that need to execute binaries. E.g.: ag, npm
(setq exec-path (append exec-path '("/usr/local/bin")))
{{< /highlight >}}

Place the above in your init.el file.

For my personal workflow and habits, this allows me to minmize window hopping, and keep more of my work in Emacs, which is always a good thing.

### Resources

https://www.emacswiki.org/emacs/ExecPath