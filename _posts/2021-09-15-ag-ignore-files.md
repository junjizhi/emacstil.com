---
layout: post
title: "counsel-ag: Ignore matches from files"
categories: [til]
comments: true
---

`ag` supports the [option](https://www.mankier.com/1/ag) `--ignore PATTERN` to ignore files/directories whose names match the pattern. We could find a way to pass this command option in as a prefix argument.

As mentioned in [searching and filtering by file name](https://emacstil.com/til/2021/09/07/ag-search/), I like to bind `(counsel-projectile-ag)` to a common shortcut,  `Super + f` (or `s-f`), so that I can pass the universal argument with `C-u` to filter results.

**Example**: To search `coffee` and ignore the matches in `org` and markdown files, I would do:

1.  Press `C-u s-f`
2.  Type `--ignore *org --ignore *md`
3.  Type search string `coffee` and press enter


