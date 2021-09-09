---
layout: post
title: "Org mode: How to fold all other headings except the current one"
categories: [til]
comments: true
---

If you are in a long org file, sometimes it's helpful to fold all other headings and focus on the current one.

There are two ways to achieve this:

1. If you don't care about  other headings, se `markdown-narrow-to-subtree`. It hides all other headings. The shortcut is `C-x n s`. To undo it, you use `C-x n w`

2. If you still want to see other headings while you are edit the current one, I found a [StackOverflow](https://stackoverflow.com/a/28031539) answer and adapted for my need:

```elisp
(defun org-show-current-heading-tidily ()
  (interactive)  ;Inteactive
  "Show next entry, keeping other entries closed."
  (if (save-excursion (end-of-line) (outline-invisible-p))
      (progn (org-show-entry) (show-children))
    (outline-back-to-heading)
    (unless (and (bolp) (org-on-heading-p))
      (org-up-heading-safe)
      (hide-subtree)
      (error "Boundary reached"))
    (org-overview)
    (org-reveal t)
    (org-show-entry)
    (show-children)))
```