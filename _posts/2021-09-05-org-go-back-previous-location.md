---
layout: post
title: "Org-mode: Go back to previous location after opening links"
categories: [til]
---

The function you are looking for is:

```elisp 
(org-mark-ring-goto)
```
I like to bind it the same as `pop-tag-mark` as in other modes, so that pressing `Ctrl` + `-` acts like going back to the previous location after you go to a definition.

For example:

```elisp
(defun jz/org-mode-hook ()
  (local-set-key (kbd "C--") 'org-mark-ring-goto))
    
(add-hook 'org-mode-hook 'jz/org-mode-hook)
```
