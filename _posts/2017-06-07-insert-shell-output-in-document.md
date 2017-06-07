---
layout: post
title: Insert shell output in document
date: 2017-06-07 07:00:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Vim can easily execute a shell command with the `!`. But you can just as easily insert the output of that command into your document.

Simply use `:.!` like so, where _command_ is whatever you want to run in your shell:
{% highlight VimL %}
:.!command
{% endhighlight %}

For example, try running the following from normal mode:

{% highlight VimL %}
:.!cal
{% endhighlight %}

The line where your cursor was will be replaced with the output of the unix `cal` command like so:

{% highlight text %}
     June 2017
Su Mo Tu We Th Fr Sa
             1  2  3
 4  5  6  7  8  9 10
11 12 13 14 15 16 17
18 19 20 21 22 23 24
25 26 27 28 29 30
{% endhighlight %}

If you'd rather insert the output into a new line below your cursor, Vim can do that, too:

{% highlight VimL %}
:r!
{% endhighlight %}
