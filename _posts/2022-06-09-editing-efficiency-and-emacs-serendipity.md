---
layout: post
title: 'Editing Efficiency and Emacs Serendipity'
date: '2022-06-09 11:44:18 -0400'
categories: [til]
comments: true
excerpt: 'I dropped the habit of having many custom keybindings, switched to use M-x, and found serendipity in Emacs.'
---

## Squeezing the tiny editing efficiency

I used to bind Super and another key with the commands / functions that
I repetitively use. It works well for the actions like
`counsel-buffer-or-recentf` which I just press `Command + T` keys in my
Mac keyboard. 

It is _a bit_ efficient than pressing M-x and type the command name.

## Is it worth it if I can't remember the keys?

I seem to have overdone it and ended up with lots of
keybindings. When I actually need to use it occasionally, my first
instinct was to try to remember what my keybinding was, and often
forgotten.

Later I realized it is better to not bind the keybindings at all.
Instead, just give the command or function a descriptive name, like
`jz/copy-relative-path`, and always use M-x.

Yes, I lose a little editing efficiency, but I form a better long-term
memory about the editing operations, and the functions available for me
to use.

## M-x and serendipity

Using M-x also comes with another unexpected benefits: With
autocomplete, I sometimes learn about better commands in the drop-down
and use them instead.

__Example__:

When I want to replace something inside a repo, I vaguely
remember projectile has something like that, so I type:
`M-x proj replace`.

Some commands show up. One is `projectile-replace` and the
other is `project-query-replace-regexp`.

At that moment, I can slow down and ask myself if I want to use regex
instead. If yes, I should pick the regex one instead.

Most Emacs commands are name meaningfully, and based on autocomplete and string
fuzzy match, we could discover the relevant commands. We should take advantage
of that.

Even if you spell brokenly, like typing partial words `proj` and
`repla`, Emacs still finds the right _spell_ for you and does its _magic_.

During the process I felt calm. I let Emacs teach me something new, and
enhance my memory about Emacs verbiage along the way.

That\'s my Emacs serendipity.
