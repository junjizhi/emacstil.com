---
layout: post
title: "counsel-ag: Search and match the whole word"
categories: [til]
comments: true
---

`ag` supports the [option](https://www.mankier.com/1/ag) \`-w\` to match the whole word. We could find a way to pass this command option in as a prefix argument.

As mentioned in [searching and filtering by file name](https://emacstil.com/til/2021/09/07/ag-search/), I like to bind `(counsel-projectile-ag)` to a common shortcut,  `Super + f` (or `s-f`), so that I can pass the universal argument with `C-u` to filter results.

**Example**: To search the word `coffee` I would do:

1.  Press `C-u s-f`
2.  Type `-w`
3.  Type search string `coffee` and press enter

