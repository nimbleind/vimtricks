---
layout: post
title: Code Reformatting
date: 2017-05-27 08:59:16
categories: Essentials
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

When I wind up with code that is not well formatted, the `=` command comes in
handy.  This command runs applies a formatter to your motion or visual
selection.  So two handy sequences of commands I keep at hand are `gg=G` and
`=%`.  The later takes advantage of the
[matchit](http://www.vim.org/scripts/script.php?script_id=39) plugin which
enhances `%` to match a broad array of open close blocks like those found in the
Ruby programming language.


{% highlight ruby %}

def read_something(filename)
      open(filename) do |fh|
fh.each_line do |line|
         puts line
end
      end
      end

{% endhighlight %}

Applying `gg=G` formats the entire file:

{% highlight ruby %}

def read_something(filename)
  open(filename) do |fh|
    fh.each_line do |line|
      puts line
    end
  end
end

{% endhighlight %}

Note that reformatting can be performed on a visual selection by hitting `=`
after selecting with `V`  

Lastly, the command that performs formatting can be set using `:set equalprg`.
See `:help =` and `:help equalprg` for more details.


