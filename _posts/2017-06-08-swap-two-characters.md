---
layout: post
title: Swap two characters
date: 2017-06-08 07:43:55
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Use `xp` to swap the character under your cursor with the one to its right.

For example, with your cursor on the misplaced _l_ in _Hlelo_, type `xp`.

{% highlight ruby %}
puts "Hlelo world!"
{% endhighlight %}

The `x` deletes the character under the cursor and puts it in a register and `p` pastes that register to the right of the cursor. You end up with:

{% highlight ruby %}
puts "Hello world!"
{% endhighlight %}
