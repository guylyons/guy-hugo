---
title: exec-path in Emacs
date: 2018-10-02T02:47:10.000+00:00
tags:
- emacs
- eshell

---
Being able to run your everyday terminal commands in eshell is really handy, but if you haven't configured **exec-shell**, you probably don't have access to them.

Similar to the $PATH variable in Bash, in Emacs you'll need to set your 'exec-path' and your "PATH" via setenv.

{{< highlight lisp >}}
;; required for exposing commands in eshell or sane term.
;; Similar to setting your $PATH in BASH
(setenv "PATH" (concat (getenv "PATH") ":/usr/local/bin"))

;; exec-path is used for Emacs programs that need to execute binaries. E.g.: ag, npm
(setq exec-path (append exec-path '("/usr/local/bin")))
{{< /highlight >}}

Place the above in your init.el file.

For my personal workflow and habits, this allows me to minimize window hopping, and keep more of my work in Emacs, which is always a good thing.

**Update:**

**You can also accomplish this with a package I've found and listed below.**

### Resources

https://www.emacswiki.org/emacs/ExecPath

[https://github.com/purcell/exec-path-from-shell]("https://github.com/purcell/exec-path-from-shell")
