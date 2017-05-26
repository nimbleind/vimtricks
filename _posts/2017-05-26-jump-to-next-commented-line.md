---
layout: post
title: Jump to the next commented line
date: 2017-05-26 07:43:55
categories: VimL
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

If you've ever needed to jump quickly to the next commented line of code,
there's a trick for that.  You'll need to add a new commands to Vim, but that's
as easy as adding a few lines to your _.vimrc_ file. The following maps `]c` to
jump to the next commented line of code and `[c` to the previous.

By using `&cms` (CoMment String) we can make this language agnostic, and it
should work in any file recognized.

{% highlight VimL %}

nnoremap ]c :call search('^\s*'.substitute(escape(&cms, '\.*[]^$'), '%s', '.*', '').'\s*$')<CR>
nnoremap [c :call search('^\s*'.substitute(escape(&cms, '\.*[]^$'), '%s', '.*', '').'\s*$', 'b')<CR>

{% endhighlight %}

Now inside a file such as this Ruby file, you can jump to the next commented
line by simply tapping `]` and `c` in succession:

{% highlight ruby %}

def foo
end

def bar(arg)
  puts "bar:"
  # something important
  puts arg
end

{% endhighlight %}

Special thanks to [Tim Pope](http://tpo.pe) for crafting this tip and to [Andrew Libby](https://github.com/alibby) for help configuring the mapping.
