---
layout: post
title: Add a line above or below
date: 2017-06-09 07:00:00
categories: Plugins
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

If you don't have Tim Pope's
[unimpaired.vim](https://github.com/tpope/vim-unimpaired), you should.
Unimpaired adds many useful pairs of mappings including one for adding an empty
line above or below your current line.

In normal mode, use `[<Space>` and `]<Space>` to add an empty line either above
or below your current line. With your cursor on the _def bar_ line below, tap
`[<Space>` and a line will be effortlessly inserted above while your cursor remains
on its line.

{% highlight ruby %}
def foo
end
def bar
end
{% endhighlight %}

{% highlight ruby %}
def foo
end

def bar
end
{% endhighlight %}
