---
layout: post
title: 'Bookmark / Star feeds in Elfeed'
date: '2021-10-31 18:23:50 -0400'
categories: [til]
comments: true
---

Recently I [switched to use elfeed](https://emacstil.com/til/2021/10/07/setting-up-elfeed-for-rss-feeds/) to manage all my RSS feeds.

Sometimes I found the interesting articles that I want to mark and save them for future. There is no built-in _starring_ features with elfeed. 

From [this Pragmatic Emacs article](http://pragmaticemacs.com/emacs/star-and-unstar-articles-in-elfeed/), I found this solution:

```elisp
;; From http://pragmaticemacs.com/emacs/star-and-unstar-articles-in-elfeed/
(defalias 'elfeed-toggle-star
  (elfeed-expose #'elfeed-search-toggle-all 'star))

(eval-after-load 'elfeed-search
  '(define-key elfeed-search-mode-map (kbd "m") 'elfeed-toggle-star))

;; face for starred articles
(defface elfeed-search-star-title-face
  '((t :foreground "#f77"))
  "Marks a starred Elfeed entry.")

(push '(star elfeed-search-star-title-face) elfeed-search-face-alist)
```

Now I can press the `m` key in the elfeed buffer and the marked feed is tagged with _star_ as well as turn `red`. 

Pretty neat!