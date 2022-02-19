---
layout: post
title: 'Use yasnippet for personal planning'
date: '2022-02-19 08:59:28 -0500'
categories: [til]
comments: true
---

[yasnippet](https://github.com/joaotavora/yasnippet) is great for coding.
It allows you to set up abbreviations and get the editor to expand to the full code.

For example, when editing Javascript code, I type `clo` and press TAB,
it would expand to:

```js
console.log("object >>>", object)
```

and then prompt me to type the `object` that I want to inspect.

**This functionality is handy in managing personal planning templates, too**!

For example, I\'m trying out [Cal Newport\'s weekly planning
method.](https://www.calnewport.com/blog/2014/08/08/deep-habits-plan-your-week-in-advance/)
For that, I have the following snippet:

    # -*- mode: snippet -*-
    # name: my weekly plan template
    # key: <wp
    # --

    * w$0
    ** Meta

    ** Work

    ** Side projects

    ** Health / Friends / Family

    * Summary & Metrics

When planning for next week, I would create new org file, e.g.,
`week8.org`, and then invoke `M-x yas-insert-template`, select
`my weekly planning template`, and start filling up the content.

> Note: I rarely use the `<wp` shorthand. That\'s because I never remember it. All I remember is
> , I have a planning template in yasnippet, and now I
> just insert it. The next move is just to invoke the right `M-x` command.

The template has nothing fancy: just some org-mode headings to remind
some important [buckets of my
life](https://www.calnewport.com/blog/2020/04/20/cultivating-a-deep-life/).

What\'s more important is, my template is _plaintext_ and
version controlled in Git, which allows to change and iterate on it as I
grow. 

And it works wonders for me.
