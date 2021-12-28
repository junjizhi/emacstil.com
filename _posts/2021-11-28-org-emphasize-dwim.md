---
layout: post
title: 'Org emphasize DWIM'
date: '2021-11-28 19:08:27 -0500'
categories: [til]
comments: true
---

How can we get org-mode to emphasize things smartly? Let's find out.

Background: After [hiding the markers and making them colorful](https://emacstil.com/til/2021/11/26/make-org-emphasis-code-verbatim-bold-look-nicer/),
I want to make the act of emphasis as easy as possible.

The `M-x org-emphasize` or `C-c C-x C-f` is close but does not meet my
expectation because:

-   It prompts me to input the marker, which
    is extra overhead
-   It requires me to mark the region first. Too much ceremony needed.

Basically, I need a command that can do what I mean
([DWIM](https://en.wikipedia.org/wiki/DWIM)).

My editing intention goes something like: **Depend on the cursor position, it
either emphasizes the current word, or starts a new emphasis region.**

I found [this SO
answer](https://emacs.stackexchange.com/a/14586). With some tweaks, I
had a working solution:

```elisp
;; Adapted from https://emacs.stackexchange.com/a/14586
(defun org-emphasize-dwim (&optional char)
  (interactive)
  (unless (region-active-p)
    (jz/maybe-mark-word))
  (org-emphasize char))

(defun org-emphasize-with-verbatim-dwim ()
  (interactive)
  (org-emphasize-dwim ?=))

(defun org-emphasize-with-code-dwim ()
  (interactive)
  (org-emphasize-dwim ?~))
```

I use `code` and `verbatim` a lot, so I created two dedicated
functions for them: `(org-emphasize-with-verbatim-dwim)` and
`(org-emphasize-with-code-dwim)`.

Below is the implementation of `(jz/maybe-mark-word)`.

```elisp
(defun jz/cursor-outside-of-any-word ()
  (not (bounds-of-thing-at-point 'word)))

(defun jz/cursor-at-beginning-of-a-word ()
  (eq (point) (car (bounds-of-thing-at-point 'word))))


(defun jz/maybe-mark-word ()
  "Mark the current word. If cursor is outside of a word bounds, mark the empty position."
  (interactive)
  (unless (or (jz/cursor-outside-of-any-word) (jz/cursor-at-beginning-of-a-word))
    (backward-word))
  (unless (jz/cursor-outside-of-any-word)
    (mark-word)))
```

**The gist is to prevent calling `(backward-word)` if the cursor is at
the beginning of a word, or outside of a word**.

Finally, I bind the functions with backtick key because I found myself
rarely use it, so I bind the keystrokes:

```elisp
(defun jz/org-mode-hook ()
  (local-set-key (kbd "M-`") 'org-emphasize-with-verbatim-dwim)
  (local-set-key (kbd "`") 'org-emphasize-with-code-dwim))

(add-hook 'org-mode-hook 'jz/org-mode-hook)
```

Right now if I press the `` ` `` or `` M-` `` key, Emacs emphasizes the
current word correctly as I like!

  > **EDIT**: When I started programming in elisp and writing macros, I found
  > the backtick is used often, and I had to unset the backtick and invoke the
  > emphasize-with-code-dwim maually with M-x instead.
