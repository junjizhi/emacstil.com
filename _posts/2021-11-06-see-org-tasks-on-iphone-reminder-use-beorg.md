---
layout: post
title: 'Sync Org Tasks to iPhone Reminder? Use Beorg!'
date: '2021-11-06 21:08:08 -0400'
categories: [til]
comments: true
excerpt: 'Sync Org TODO / tasks or agenda with iPhone. Integrates with icloud  / Reminder.app.' 
---

If you use org-mode and own an iPhone, a natural thought is to view the tasks on the phone.

Sometimes I'm just too lazy to open the laptop lid and run
`org-agenda`.

[beorg](https://beorgapp.com/) works reasonably well for me.

Beorg has the interface that shows the tasks from both Reminder and org
files. Set up iCloud to store the files.

Then _pipe_ all the TODO captures to the iCloud path:

``` elisp
(setq beorg-file "~/Library/Mobile Documents/iCloud~com~appsonthemove~beorg/Documents/org/inbox.org")
(setq org-capture-templates
      '(("t" "Todo" entry (file+headline beorg-file "Tasks")
         "* TODO %?\n  %i\n  %a")))
```

Screenshot:

![beorg](https://beorgapp.com/images/blog/beorg3_5-selecting.jpg)

(Image courtesy: beorgapp.com)

Enjoy org files on the go!
