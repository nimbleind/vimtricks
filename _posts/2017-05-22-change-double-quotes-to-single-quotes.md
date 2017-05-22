---
layout: post
title: Change double quotes to single quotes
date: 2017-05-22 09:03:00
categories: Plugins
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Changing double quotes to single quotes or vice versa in Vim is simple if you have [tpope](http://tpo.pe/)'s [surround.vim](https://github.com/tpope/vim-surround) plugin.

With the plugin installed and your cursor anywhere inside a quoted string press `cs` followed by the character you want to change and then the character you want to change it to. You can remember this with the mneumonic Change Surrounding.

For example, `cs"'` with your cursor inside the _\"Content-Type\"_ string would change it like so:

{% highlight javascript %}

// from
req.setRequestHeader("Content-Type", "application/json")

// to
req.setRequestHeader('Content-Type', "application/json")

{% endhighlight %}

You can then repeat the action for the next one by simply pressing `.` in place.
