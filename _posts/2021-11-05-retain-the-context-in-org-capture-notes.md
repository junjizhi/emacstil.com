---
layout: post
title: 'Retain the Context in Org Capture notes'
date: '2021-11-05 20:13:02 -0400'
categories: [til]
comments: true
tags: [org,org roam,template expansion,org capture]
---

When we capture an idea, it's useful to keep the context. 

When we go back to the notes later, we don't waste time to dig the context and look for details. 

It's convenient that all things are _just there_ when we need it.

In org capture template, I found the [template expansion](https://orgmode.org/manual/Template-expansion.html) `%a` good enough for this purpose.

```
‘%a’

    Annotation, normally the link created with org-store-link.
```

My org capture template looks something like:

```elisp
(setq org-capture-templates
      '(("t" "Todo" entry (file+headline "~/org/gtd.org" "Tasks")
         "* TODO %?\n  %i\n  %a")
       ("n" "Note" entry
          (file+headline "~/org/notes.org" "Notes")
          "* %?
** Content

** References
- %a

%T
")))
```

When I fire `M-x org-capture` command and choose `note`, the capture buffer will something like:

```
** 
*** Content

*** References
- [[file:~/../_posts/2021-11-05-retain-the-linkcontext-in-org-capture-notes.md][:~/../_posts/2021-11-05-retain-the-linkcontext-in-org-capture-notes.md]]

<2021-11-05 Fri 20:30>

```

It has two sections,  one for content and the other for references, where it links to the buffer where the idea was generated.

The links works well [Magit](https://magit.vc/) commit diffs or [elfeed](https://github.com/skeeto/elfeed) RSS articles, too. This is especially useful for developers who have ideas while deep in the code or reading a RSS feed.

If you use [org-roam](https://github.com/org-roam/org-roam), The same template works for [org-roam-capture](https://github.com/org-roam/org-roam/blob/master/org-roam-capture.el), too!

With this tweak, you can jot down ideas quickly, commit and forget. Rest assured Org keeps the context for you!