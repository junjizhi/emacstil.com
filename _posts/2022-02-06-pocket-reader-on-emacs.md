---
layout: post
title: 'Pocket Reader on Emacs'
date: '2022-02-06 11:26:47 -0500'
categories: [til]
comments: true
excerpt: 'Read Pocket articles on Emacs. Mark them in Firefox or elfeed, and read them later on Emacs.'
---
I found this gem:
[pocket-reader.el](https://github.com/alphapapa/pocket-reader.el). It is
one of those low-key packages that _just works_.
Kudos to [alphapapa](https://github.com/alphapapa)!

[pocket-reader.el](https://github.com/alphapapa/pocket-reader.el) does
what it says: It allows you to read [Pocket](https://getpocket.com/) articles on Emacs. If you use
Firefox, it\'s handy because [Pocket is built in on
Firefox](https://support.mozilla.org/en-US/kb/disable-or-re-enable-pocket-for-firefox).
All you have to do is sign up a Pocket account and authorize
pocket-read.el.

<img width="356" alt="image" src="https://user-images.githubusercontent.com/2715151/152690918-cb2a0c7a-f741-4ea2-b832-dab72ceadcd4.png">

Then you are just a button click away from saving articles and reading
them later.

![pocket-read.el demo](https://raw.githubusercontent.com/alphapapa/pocket-reader.el/master/screenshots/default-theme.png)
_(image source: [pocket-reader.el](https://github.com/alphapapa/pocket-reader.el))_

This setup requires you change your habit to the Read-it-Later flow. If
you are not familiar, [Tiago Forte has a good post explaining this
flow](https://fortelabs.co/blog/the-secret-power-of-read-it-later-apps).

It feels liberating for me to know that an app remembers the interesting
long-form writings, and I can come back any time in the future,
_on Emacs_!

What\'s interesting is,
[pocket-reader.el](https://github.com/alphapapa/pocket-reader.el)
integrates well with
[elfeed](https://emacstil.com/til/2021/10/07/setting-up-elfeed-for-rss-feeds/),
as I can save an elfeed entry to pocket, and read it later like any
other web articles.

Happy reading!
