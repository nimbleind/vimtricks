---
layout: post
title: Scroll two splits simultaneously
date: 2017-06-12 07:00:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

If you've ever diffed a file in Vim or otherwise had two corresponding splits,
you may have wished for a way to scroll them together. Vim can do just that
with `scrollbind`.

With `scrollbind` enabled, each window in Vim will scroll simultaneously. Line
for line as you move through the file, the other window will scroll as
well.<sup>[1](#citation1)</sup>

Simply run the following:

{% highlight VimL %}
:set scrollbind
{% endhighlight %}

Or to put it back:

{% highlight VimL %}
:set noscrollbind
{% endhighlight %}

You can also toggle the option with:

{% highlight VimL %}
:set scb!
{% endhighlight %}

<sub><a id="citation1">1</a>. Scrolling synchronously. (n.d.). In Wikia.
Retrieved June 11, 2017, fron
[http://vim.wikia.com/wiki/Scrolling_synchronously](http://vim.wikia.com/wiki/Scrolling_synchronously)</sub>
