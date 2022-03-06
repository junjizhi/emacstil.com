---
layout: post
title: 'Emacs: How to go to line N'
date: '2022-02-24 01:06:16 -0500'
categories: [til]
comments: true
excerpt: 'This post explains how to go to a line in vanilla and Doom Emacs. The simplest way is M-x goto-line'
---
When working on Emacs, we often need to move the cursor to certain line. This post explains how to do that in vanilla and Doom Emacs. 

In Vi, you just type colon + number, like `:14` to go to line 14.

Things in Emacs are more interesting.

In Vanilla Emacs, you can invoke the `M-x`, and then type out the
command `goto-line` and enter a number for the line.

Or, you can use the shortcut: `M-g g`.

Doom Emacs keeps similar keybindings. If you type `C-h k M-g g` to
describe the `goto-line` function, you see all the existing key
bindings:

    Key Bindings
    esc-map g M-g
    esc-map g g
    global-map M-g M-g
    global-map M-g g
    goto-map M-g
    goto-map g

Clearly Doom Emacs binds extra keys to be more tolerant of user errors,
e.g., pressing the second g key while the meta key is not released yet.

In Mac OS X, I like to bind `s-l` to `goto-line` so that I can press
`command + l` to do the same thing, instead of pressing the
awkward combo of M-g g.

__Edit__:

Malcolm Purvis commented that we can use `C-u <number> M-x goto-line` to enter
the line number first. That is a nicer workflow if you are comfortable with Emacs
[prefix arguments](https://www.gnu.org/software/emacs/manual/html_node/elisp/Prefix-Command-Arguments.html).
