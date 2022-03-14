---
layout: post
title: 'Process Org Files Programmatically'
date: '2022-03-13 15:44:52 -0400'
categories: [til]
excerpt: 'This post talks about how to write elisp code to read *.org files, including looping through headings, get org file properties, building complex search queries.'
comments: true
---

Writing some elisp code can go a long way to automate org files related tasks, espeically when your org files are structured. 

I list my notes below about the commonly used elisp functions. They 

## Loop through org headings with `org-map-entries`

[The org-mode API
doc](https://orgmode.org/manual/Using-the-Mapping-API.html) is a bit
short and doesn\'t contain examples. But `org-map-entries` is convenient
to loop through headings.

The usage is something like:

``` elisp
(find-file "test.org")
(org-map-entries
 'my-function                           ; Apply to every entry
 "+LEVEL=1")
```

The above snippet loops through all top-level headings and apply
`my-function` to each heading.

For the definition `my-function`, it doesn\'t accept any argument.
Instead, you assume the `point` is at the beginning of the
heading, and invoke editing function accordingly.

As a made-up example, we could add the updated timestamp under each top
level heading (and define the editing function as a lambda):

``` elisp
(find-file "test.org")
(org-map-entries
 (lambda ()
   (newline-and-indent)
   (insert (format "Edited at %s" (format-time-string "%Y-%m-%d %H:%M")))
   (newline-and-indent))
 "+LEVEL=1")
```

Note that `"+LEVEL=1"` here is the argument for _MATCH_ argument.
Fortunately, [the Org
Manual](https://orgmode.org/manual/Matching-tags-and-properties.html)
has good examples to show how to build _matching tags and
properties_ string.

You can build complex matching logic based on tags and properties. For
example, the following string:

> +LEVEL=2+work-boss+PRIORITY=\"A\"

matches any level two heading with a \"work\" tag and property \"A\",
yet without a \"boss\" tag.

## Get org file title

Use `org-collect-keywords`:

``` elisp
(cadar (org-collect-keywords '("TITLE")))
```

## Move current heading (and all its subheadings) down a level

Use `org-demote-subtree`.
