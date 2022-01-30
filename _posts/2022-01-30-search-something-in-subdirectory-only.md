---
layout: post
title: 'Search something in sub-directory only'
date: '2022-01-30 00:12:22 -0500'
categories: [til]
comments: true
---

Recently I worked in a giant Rails monolith repo. When I say giant, it
means multiple teams owning different modules inside the rails, and
there are thousands of files.

As a result, doing `+ivy/project-search` is not efficient because it
searches the entire project and shows too many irrelevant results.

Because most teams touch files in a sub-directory only, we could narrow the
search to a sub-directory, which makes the search more useful.

**My solution: `C-u counsel-rg`**.

With the prefix, the command asks for the input of a folder first. If
you visit a sub-directory often, use `M-p` to go to previous input
without typing.

It then shows the hits of files under the sub-directory only.

It is based on `ripgrep`, so it supports regex based filter (Credit:
[Reddit](https://www.reddit.com/r/emacs/comments/gr72by/comment/frzcdcb/?utm_source=share&utm_medium=web2x&context=3)).
For example, search `keyword` in `jsx` files only:

`keyword -- -g\*.jsx`

From there on, we can do `C-c C-e` to do bulk edits or search & replace
to deal with the results.
