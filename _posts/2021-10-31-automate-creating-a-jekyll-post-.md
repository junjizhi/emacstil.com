---
layout: post
title: 'Automate Creating a Jekyll Post'
date: '2021-10-31 18:41:26 -0400'
categories: [til]
comments: true
---

To get myself write more, I want to make creating a blog post as painless as possible.

Since I'm using [Jekyll](https://jekyllrb.com/) to run my blog, the process of creating a Jekyll blog post is as follow:

1. Create a new file in `_posts` folder, for example, `_posts/2021-10-31-automate-creating-a-jekyll-post.md`
2. Fill in the file headers with settings like `layout`, blog `title`, etc.

It is a repeated task. What if we can automate it?

I found [this Gist](https://gist.github.com/tpanum/f1bcd76cfdc6d3f3b28a) and adapted to fix my needs. You can tweak the `blog-home` variable and the file content as well.

```elisp
;; Adapted from https://gist.github.com/tpanum/f1bcd76cfdc6d3f3b28a

(setq blog-home "/<path>/<to>/emacs-til)

(defun jz/create-jekyll-post-emacs-til
  (title)
  "Creates a new buffer and file for an Emacs TIL blog post"
  (interactive "sTitle of blog post: ")
  (let
    ((filename
       (concat
         (format-time-string "%Y-%m-%d-")
         (replace-regexp-in-string " " "-"
           (downcase
             (replace-regexp-in-string "[^0-9a-zA-Z ]" "" title))))))
    (switch-to-buffer
      (generate-new-buffer filename))
    (insert
      (concat
        (mapconcat 'identity
          '("---" "layout: post")
          "\n")
        "\n" "title: '" title "'\n" "date: '"
        (format-time-string "%Y-%m-%d %H:%M:%S %z")
        "'\n" "categories: [til]"
        "\n" "comments: true"
        "\n" "---\n"))
    (write-file
      (concat blog-home "/_posts/" filename ".md"))))
```

With this, writing a blog post is just one command away. Press `M-x` and run `jz/create-jekyll-post-emacs-til`. 

It prompts me to enter the blog title and create the file with templated content:

```
---
layout: post
title: 'Automate Creating a Jekyll Post'
date: '2021-10-31 18:41:26 -0400'
categories: [til]
comments: true
---
```



Let the writing flow!
