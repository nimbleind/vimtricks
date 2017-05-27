---
layout: post
title: Retain indentation in pasted code
date: 2017-05-27 07:57:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

When pasting into Vim from an external source, for example when using ⌘-V in a
terminal on macOS, you'll find that pasted text loses its indentation.

That's because Vim has no way to distinguish that the text you're entering was
pasted and not just typed in. Therefore, normal autoindenting and other
formatting will be applied, destroying the existing indentation. Except, Vim
does indeed have a way to distinguish pasted text!

{% highlight VimL %}
:set paste
{% endhighlight %}

Simply turn on the paste option with `:set paste` and any text pasted from your
system clipboard in insert mode will be entered as-is without additional
indentation rules applied. You can revert to the original with `nopaste`

{% highlight VimL %}
:set nopaste
{% endhighlight %}
