---
layout: post
title: Jump to matching parenthesis
date: 2017-06-04 08:48:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Vim has a simple way to jump to the corresponding opening or closing
parenthesis: `%`. Your cursor will effortlessly bounce from closing to opening
or vice versa.

This works for other types of braces and brackets as well. When positioned on
one of a pair of _[]_, _{}_, or _()_, simply press the percent key `%` to jump
the cursor to the matching opening or closing character. Vim calls these
_matchpairs_.

You can see what pairs of characters Vim knows about by inspecting the `matchpairs`
attribute with `:set matchpairs`. This can vary from buffer to buffer depending on
the filetype. In the case of a Markdown file my current config shows:

{% highlight VimL %}
matchpairs=(:),{:},[:],<:>
{% endhighlight %}

You may notice that the corresponding character your cursor moves to is already
highlighted by Vim before jumping. That's because Vim includes a standard
plugin called _matchparen_, which will highlight the matching parens.

If for some strange reason you don't like this functionality, you can disable
it with simply:

{% highlight VimL %}
:NoMatchParen
{% endhighlight %}

Or enable it if it's already disabled:
{% highlight VimL %}
:DoMatchParen
{% endhighlight %}

For more information, such as how to change the colors, see `:help matchparen`.
