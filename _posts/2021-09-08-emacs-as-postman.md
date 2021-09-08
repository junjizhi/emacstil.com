---
layout: post
title: "Use Emacs like Postman for API testing"
categories: [til]
comments: true
---


Doom Emacs has the [restclient](https://github.com/pashky/restclient.el) mode support for org-mode code block. To turn it on, uncomment the `rest` under `:lang` in `init.el`.

Then we can do something like in an `*.org` file:

```
#+begin_src restclient
GET https://jsonplaceholder.typicode.com/todos/1
#+end_src
```
    

After pressing `C-c C-c`, we see the results as in plain text:

```
{
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
// GET https://jsonplaceholder.typicode.com/todos/1
// HTTP/1.1 200 OK
// Date: Tue, 08 Sep 2021 18:18:38 GMT
// Content-Type: application/json; charset=utf-8
// Transfer-Encoding: chunked
// ...
```
