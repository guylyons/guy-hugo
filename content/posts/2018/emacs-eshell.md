---
title: Emacs eshell
date: 2018-10-02T02:47:10.000+00:00
tags:
- emacs
- eshell

---
Eshell is the Emacs terminal emulator written 100% in elisp. It's much faster than ansi-term or sane-term, and has some added benefits other than just speed[^1].

If your on a Mac, you might not have access to some of the command you do in BASH, because you need to configure
your exec-path. Similar to the $PATH variable in BASH, exec-path is a user defined value in Emacs that can take
an array of directories that you want to expose for executing their binaries.

{{< highlight lisp >}}
;; required for exposing commands in eshell or sane term.
;; Similar to setting your $PATH in BASH
(setenv "PATH" (concat (getenv "PATH") ":/usr/local/bin"))

;; exec-path is used for Emacs programs that need to execute binaries. E.g.: ag, npm
(setq exec-path (append exec-path '("/usr/local/bin")))
{{< /highlight >}}

While this solution works just fine, there is also a package "exec-path-from-shell"[^2]
that is a bit more automatic.

### Resources

https://www.emacswiki.org/emacs/ExecPath

http://ergoemacs.org/emacs/eshell.html

[^1]: https://www.masteringemacs.org/article/complete-guide-mastering-eshell

[^2]: https://github.com/purcell/exec-path-from-shell