---
layout: post
title: 'Run grammar check on Org buffers automatically with Language-Tool  '
date: '2022-03-05 21:28:44 -0500'
categories: [til]
comments: true
---
I
[blogged](https://emacstil.com/til/2021/11/11/setting-up-grammar-check-with-doom-emacs-in-mac-os-x/)
about my LanguageTool setup a while ago. The default workflow is to invoke `M-x
langtool-check-buffer` when I like it. But I find it too manual. So I set it up
to run the check automatically right before saving an Org buffer.

The trick is to add it as a
[before-save-hook](https://emacs.stackexchange.com/a/5777) for org-mode:

``` elisp
(defun jz/org-mode-hook ()
  ;; Check grammar with langtool before save
  (add-hook 'before-save-hook 'langtool-check-buffer nil 'local))

(add-hook 'org-mode-hook 'jz/org-mode-hook)
```

With this, every time I save an org buffer, it runs the langtool check.
All errors are highlighted, and I can invoke
`M-x langtool-correct-buffer` to fix the errors one by one.

It works nicely alongside [my Vale style linter](https://emacstil.com/til/2022/03/05/setting-up-vale-prose-linter-on-emacs/):

![Running language-tool automatically on org-mode, alongside Vale prose linter on Emacs and display linting errors](https://user-images.githubusercontent.com/2715151/156907052-34320650-7992-40c1-aeaa-b7806cabf0eb.png).
