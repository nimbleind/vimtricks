---
layout: post
title: Open Vim with no plugins
date: 2017-06-02 07:00:00
categories: Plugins Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Ever need to debug something with you Vim config or ever wonder if your favorite Vim trick is available in stock Vim? There's a simple way to load vim without any plugins:

{% highlight text %}
$ vim -u NONE
{% endhighlight %}

This will open vim without your _.vimrc_ and with no plugins enabled. It's stock Vim with no customization whatsoever.

There are other ways to open vim loading just _.vimrc_ or just plugins and the Vim documentation has a simple chart to show them:

|  Argument    | Load vimrc files? | Load plugins? |
|--------------|:----------------:|:------------:|
| (nothing)    |        yes       |      yes     |
| `-u NONE`    |         no       |       no     |
| `-u NORC`    |         no       |      yes     |
| `--noplugin` |        yes       |       no     |
