---
layout: post
title: Disable unsaved hidden buffers
date: 2017-06-01 07:44:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Did you ever scratch your head thinking, "I'm sure I made that change... but
now it's gone!"? You may have fallen victim to `:set hidden`. Save yourself
headaches with this one simple Vim trick.

With `hidden` set on, any file you edit but don't save will stick around in Vim
as an unsaved buffer when you navigate away from it. This means that Vim has
your changes in memory but has not written them to disk. This might be helpful
for some who want to toggle back to another file before saving their changes,
but many people would prefer not to worry about losing work they forget to
save. And in our modern era, everything is version-controlled so there's less
danger in writing a file prematurely.

In your _.vimrc_ file, add the following line to disable unsaved, hidden
buffers:

{% highlight VimL %}
set nohidden
{% endhighlight %}

Now, if you try to navigate away from a file and you have not saved your
changes, you'll get the typical _No write since last change_ error, prompting
you to save before hiding the buffer. You'll also never be surprised by a `:q!`
or `:wa` again.
