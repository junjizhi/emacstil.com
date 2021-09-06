---
layout: post
title: "Magit: Copy Github links to current link / file"
categories: [til]
comments: true
---

In VSCode, there is a plugin to copy [Git Web Links for VS Code](https://marketplace.visualstudio.com/items?itemName=reduckted.vscode-gitweblinks). It is handy when you want to share the link to a specific line of a shared code base.

In `Magit` and `Doom Emacs`, you can use the Elisp function to do the similar thing:

```elisp
(+vc/browse-at-remote-kill)
```
    

By default, it copies the URL to the file.

If you want the URL to point to **the current line**, use the keyboard shortcut:

1.  Mark current line or region you can include, and then press:
2.  `C-c v y`

