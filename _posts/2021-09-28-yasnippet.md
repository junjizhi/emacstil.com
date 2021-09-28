---
layout: post
title: "Insert Templated Code Blocks with Yasnippet"
categories: [til]
comments: true
---

When editing org file with code blocks, sometimes we want to print out the stdout, pipe the output to a file. As a result, we may type `:results` option near the code block a lot. 

This post is about using the power of [Yasnippet](https://joaotavora.github.io/yasnippet/snippet-development.html) to streamline the workflow.

Below is my snippet for inserting a scripting code block and set the `result` to output:

```
# key: <so
# name: src-script
# --
#+begin_${1:$$(yas-choose-value '("src"))} ${2:$$(yas-choose-value '("bash" "ruby" "elisp"))} :results output
  $0
#+end_$1

```

Now if I type `<so` and press `TAB`, it expands the block, prompts me to select language, or to enter the name of output file. 

Example of going through the `<so` flow and selecting bash:

```
#+begin_src bash :results output
echo "test"
#+end_src
```

_Note:_ There was a small quirks with `#begin_src` block when inserting as a plaintext, so I create the extra field to disable eval error. It results in an extra enter keystroke and a TAB, but it is good enough for my use.