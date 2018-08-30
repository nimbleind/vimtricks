---
layout: post
title: Stay in search mode
date: 2018-05-31 10:05:30
categories: Essentials
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

How I search for patterns in VIM just improved a bit today.  Generally I'd
search like so:

{% highlight plain %}

/some_pattern<CR>

{% endhighlight %}

Hitting `<CR>` exits search mode, and refining the search requires one to enter
search mode using `/` followed by the up arrow allowing refinements to the
search.  

Today I learned about `<C-g>` and `<C-t>` which will jump to the next occurrence
of the current pattern while focus is still in the search box.  This can allow
for a search workflow that allows one to jump through search hits and refine the
search more efficiently.

For more helpful tips see `:help incsearch`.




