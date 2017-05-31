---
layout: post
title: Remove trailing whitespace
date: 2017-05-31 08:33:00
categories: Plugins
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Does trailing whitespace make your blood boil? Although there are plenty of
ways to automatically trim trailing whitespace when committing, or even to hide
whitespace in diffs, you can easily trim whitespace in Vim with a simple plugin.

[Vim SpaceJam](https://github.com/rondale-sc/vim-spacejam), which was [born of
the dotfiles](https://github.com/hashrocket/dotmatrix/commit/c6a10be91e46e918b0f3d83aa10d53a2c6930e24)
of software consultancy [Hashrocket](https://hashrocket.com/), offers a very simple
solution to a very common problem: extra spaces at the end of lines. A simple command
will clear any tabs or spaces erroneossly left at the end any line in the file:

{% highlight VimL %}
:Trim
{% endhighlight %}

You can also visual select specific lines to trim only from your selection. But a simple
`:Trim` will clean up the whole file, leaving your lines minty fresh before you even
leave the buffer.
