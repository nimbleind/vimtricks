---
layout: post
title: Jump to matching parenthesis, Part 2
date: 2017-06-05 07:00:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

In addition to [jumping to the corresponding
paren](/essentials/2017/06/04/jump-to-matching-parenthesis/) with `%`, Vim has
another little-known feature for showing corresponding parens when inserting.

Vim's _showmatch_ feature might be useful for those writing code with many
nested parentheses, such as Lisp. With `:set showmatch` enabled, while in
insert mode after typing a paren, brace, or bracket, the cursor will
automatically jump to the matching brace briefly. Just long enough for you to
confirm which parenthesis you are closing.

You can change the time the cursor spends there before bouncing back with
_matchtime_.

{% highlight VimL %}
:set showmatch
:set matchtime=3
{% endhighlight %}

And if you're working on a tiny screen, or text with parens that span many
lines, you may wish to have the screen scroll automatically when _showmatch_ is
enabled. <sup>[1](#citation1)</sup>

Add this to your _.vimrc_:

{% highlight VimL %}
inoremap } }<Left><c-o>%<c-o>:sleep 500m<CR><c-o>%<c-o>a
inoremap ] ]<Left><c-o>%<c-o>:sleep 500m<CR><c-o>%<c-o>a
inoremap ) )<Left><c-o>%<c-o>:sleep 500m<CR><c-o>%<c-o>a
{% endhighlight %}

<sub><a id="citation1">1</a>. Move to matching braces. (n.d.). In Wikia.
Retrieved June 4, 2017, from
[http://vim.wikia.com/wiki/Moving_to_matching_braces](http://vim.wikia.com/wiki/Moving_to_matching_braces)</sub>
