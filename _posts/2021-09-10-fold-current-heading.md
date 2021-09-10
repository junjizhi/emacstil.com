---
layout: post
title: "Org mode: How to fold current heading"
categories: [til]
comments: true
---

If you are editing the current heading, and you are done with it, you want to fold it, and move on. 

The simple solution is just: 

```
(org-previous-visible-heading)
(org-cycle)
```

Or in shortcuts:
```
C-c C-p
TAB
```
