---
layout: post
title: "Org Mode + Mermaid"
categories: [til]
comments: true
---


It&rsquo;s neat to be able to render diagrams and flowcharts from text, which leads us to  [Mermaid.](https://mermaid-js.github.io/mermaid/#/)

## Installation

Follow [installation steps](https://github.com/mermaid-js/mermaid-cli) to install `mermaid-cli`.

If you are in Mac OS X, run:

    brew install mermaid-cli

Then install [ob-mermaid](https://github.com/arnm/ob-mermaid) package in Emacs.

Remember to set the mermaid CLI executable path:

```elisp
(setq ob-mermaid-cli-path "/usr/local/bin/mmdc")
```

## Usage

In any org file, you can use \`mermaid\` source type, and specify the output file&rsquo;s name:

```
#+begin_src mermaid :file test.png
sequenceDiagram
 A-->B: Works!
#+end_src
```

Inside the code block and press `Ctrl-c Ctrl-c`, and you would see:

<img width="752" alt="image" src="https://user-images.githubusercontent.com/2715151/133936929-69157a43-d3c4-43f6-b4b8-3f81a29ebc5a.png">


*Note*: I found Emacs doesn't render `*.svg` files well, so for the source block I always use `*.png`, which renders well enough for my use. 