---
layout: post
title: "Org-roam: Turn heading into a node"
categories: [til]
comments: true
---

When editing in [org-roam](https://github.com/org-roam/org-roam) mode, when a heading becomes prominent, you sometimes want to make it a node. Doing so means you can link it in other nodes.

To do so, move the cursor to the heading, and run: 

```elisp
(org-id-get-create)
```