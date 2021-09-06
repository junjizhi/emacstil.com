---
layout: post
title: "Doom Emacs: Search variable/function/etc. at cursor position"
categories: [til]
comments: true
---

When your cursor is on a variable / function / etc., you want
to search it in the entire project.

A cumbersome way is to mark and copy the current thing, and then invoke `counsel-projectile-ag`. 

In Doom Emacs, you can do this in one step:

```elisp
(+default/search-project-for-symbol-at-point)
```

Or use the shortcut: `C-c p .`.

