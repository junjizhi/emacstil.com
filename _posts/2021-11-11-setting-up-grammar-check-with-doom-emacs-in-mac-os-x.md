---
layout: post
title: 'Setting up grammar check with Doom Emacs in Mac OS X'
date: '2021-11-11 18:24:06 -0500'
categories: [til]
comments: true
---

Doom Emacs supports [grammar
check](https://github.com/hlissner/doom-emacs/tree/develop/modules/checkers/grammar)
with [Language Tools](https://github.com/mhayashi1120/Emacs-langtool)
and [writegood-mode.](https://github.com/bnbeckwith/writegood-mode)

To turn it on, we update the init.el:

``` elisp
:checkers
;; ...
grammar
```

Also it requires setting up java and Language Tools:

``` bash
brew install java languagetool
```

However, the language tool didn\'t work out of box with the default
Homebrew install. It complains:

    LanguageTool exited abnormally with code 1 (The operation couldn t be completed. Unable to locate a Java Runtime.)

I have to manually update the `java` executable:

``` elisp
(setq langtool-java-bin "/usr/local/opt/openjdk/bin/java")
```

Then running `M-x langtool-check-buffer` works!

__Edits on 2022-03-05__:

If you are looking for writing style linting, check out my post about [setting up vale prose linter](https://emacstil.com/til/2022/03/05/setting-up-vale-prose-linter-on-emacs/).
