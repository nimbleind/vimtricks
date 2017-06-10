---
layout: post
title: Fold a code block
date: 2017-06-10 07:00:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Vanilla Vim allows you to easily fold up blocks of code to save screen space
with `:fold`.

To use it, simply select multiple lines by entering visual select mode with
`Shift-v` and then using `:fold`. For example:

{% highlight ruby %}
def foo
  # some
  # very
  # long
  # method
end
{% endhighlight %}

...will fold down to:

{% highlight text %}
+--  6 lines: def foo------------------------------------
{% endhighlight %}

And you can then reopen it with `zo` or close it again with `zc`.
