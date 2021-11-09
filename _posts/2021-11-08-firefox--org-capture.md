---
layout: post
title: 'Firefox -> Org Capture'
date: '2021-11-08 20:17:54 -0500'
categories: [til]
comments: true
---
When you are reading an article in a webpage, you come across an idea
and want to org-capture the words/sentences. What do you do?

## Naive way
An intuitive way is highlight the content you want to capture, copy it,
switch to Emacs, run `org-capture` and yank it there.

Would it be nice if our browser sends content to `org-capture` directly
with a shortcut?

## Org-protocol and custom JS

[Org-protocol](https://orgmode.org/worg/org-contrib/org-protocol.html)
is the backbone here. The basic ides is
navigate to a link with the org-capture protocol header and the OS figures
out Emacs is the app to open it.

Now that the underlying mechanism is there, our next step is figure out the
script that drives it.

[Org-protocol docs about Mac OS
X](https://orgmode.org/worg/org-contrib/org-protocol.html#orgb7ef958) is
a bit out of date, but it has hints about the Javascript logic:

```js

document.location.href = 'org-protocol://capture://' +
  encodeURIComponent(location.href) + '/' + 
  encodeURIComponent(document.title) + '/' + 
  encodeURIComponent(window.getSelection());
```

From here, it becomes the question of how to run the custom JS code.

There are two ways:

## Method 1: Bookmarklet

Use
    [Bookmarklet](https://en.wikipedia.org/wiki/Bookmarklet) and make it
    a button in the bookmark bar

![Create a bookmarklet with custom
JS](https://cdn.jsdelivr.net/gh/junjizhi/emacstil.com@main/uPic/jLNztM.png)

The JS code is similar but has to be wrapped with a `javascript` prefix:

```js
javascript:(function(){document.location.href='org-protocol://capture://'+encodeURIComponent(location.href)+'/'+encodeURIComponent(document.title)+'/'+encodeURIComponent(window.getSelection());})();
```

With it, you can highlight some text on a page and hit the bookmark on
your toolbar. It will send to your org capture buffer right away

## Method 2: Use [ShortKeys](https://addons.mozilla.org/en-CA/firefox/addon/shortkeys/)
    
You can assign a shortcut to run custom JS

![Shortkeys
settings](https://cdn.jsdelivr.net/gh/junjizhi/emacstil.com@main/uPic/CNeplc.png)

Now I can highlight any text on a weg, then press
`ctrl-i`{.verbatim}.

Boom, it shows in the beautiful org-capture buffer.

> **_NOTE:_**   [Org-protocol](https://orgmode.org/worg/org-contrib/org-protocol.html) supports `org-store-link` and `org-remember` URLs as well. You can build URLs with the similar JS code.