---
layout: post
title: 'Set up Vale prose linter on Emacs'
date: '2022-03-04 22:17:00 -0500'
categories: [til]
comments: true
---
Most of my writing happens in [Emacs Org-mode](https://orgmode.org/).
One natural thinking is to let Emacs help me with my writing. This post
documents my attempt to set up [Vale](https://github.com/errata-ai/vale)
on Emacs, which lints prose based on the configured writing styles.

First, we need to install [Vale](https://github.com/errata-ai/vale). If
you are in Mac OS X, `brew install vale` should do the trick.

Next is to set up `.vale.ini` file in your home directory, and set up
the `styles` folder. To save time, you can clone the
[vale-boilerplate](https://github.com/errata-ai/vale-boilerplate) repo,
which comes with [Microsoft](https://github.com/errata-ai/Microsoft)
styles. Personally, I use
[proselint](https://github.com/errata-ai/proselint).

Your `$HOME/.vale.ini` should look like:

    StylesPath = styles

    Vocab = Blog

    [*.org]
    BasedOnStyles = Microsoft

We set up `flycheck` + `Vale`. I found the setup from
[Duncan\'s
post](https://duncan.codes/posts/2020-09-14-prose-linting-vale-emacs.org/index.html)
that works for me:

``` elisp
(flycheck-define-checker vale
  "A checker for prose"
  :command ("vale" "--output" "line"
            source)
  :standard-input nil
  :error-patterns
  ((error line-start (file-name) ":" line ":" column ":" (id (one-or-more (not (any ":")))) ":" (message) line-end))
  :modes (markdown-mode org-mode text-mode)
  )
(add-to-list 'flycheck-checkers 'vale 'append)
```

Add the snippet to your Emacs setup, reload, and voila!

![Running Vale linter on Emacs and display linting errors](https://user-images.githubusercontent.com/2715151/156865975-acf69d10-46d0-4066-8aad-2a3a1cad2e63.png).

> P.S. I tried following the post [Using Vale With Emacs for Prose
> Linting](https://notes.alexkehayias.com/using-vale-with-emacs-for-prose-linting/),
> but didn\'t get it to work.
>
> I also tried
> [flycheck-vale](https://github.com/abingham/flycheck-vale) package,
> but it didn\'t work either.
