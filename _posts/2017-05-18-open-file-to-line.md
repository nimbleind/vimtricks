---
layout: post
title: "Open file to line"
date: 2017-05-18 14:01:05
categories: Essentials
author:
  name: 'Andy Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

Many know about that you can open a file based on what's under your cursor using
`gf`, or `C-w f`.  There is also a handy variation on this using 'F'.  This variation will open
said file, but if it's followed by a line number vim will jump to that line.  We encounter this
a lot when executing tests via vim-dispatch.  

Say you're in a log file which contains file references:


{% highlight ruby %}

app/models/product.rb:35

{% endhighlight %}

With your cursor sitting anywhere on the line containing the file name, use `gF`.  You'll
be transported to product.rb, line 35.  Saving steps is saving time.

