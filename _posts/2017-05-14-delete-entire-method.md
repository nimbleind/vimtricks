---
layout: post
title: "Delete entire method"
date: 2017-05-14 07:43:55
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

A very common practice when refactoring code is deleting entire methods or code blocks en masse. One might be tempted to use visual select mode to select multiple lines, or simply to mash `dd`. But Vim makes deleting code blocks easy with `dap`. You can remember this as "Delete A Paragraph".

This will delete every line before and after your current line until an empty line in either direction. It will also remove any extra empty trailing lines. For example, take the following ruby code:

{% highlight ruby %}
def foo
  puts "Hello world!"
end

def bar
 %w(foo bar bat baz).each do |word|
    puts word
  end
end


def bat(baz)
  puts "#{baz}!"
end
{% endhighlight %}

With your cursor anywhere in the second method above, typing `dap` will delete the _bar_ method and leave you on _bat_ method where you can repeat with `.` to keep deleting methods:

{% highlight ruby %}
def foo
  puts "Hello world!"
end

def bat(baz)
  puts "#{baz}!"
end
{% endhighlight %}
