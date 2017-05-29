---
layout: post
title: Sorting Text
date: 2017-05-29 08:28:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Keeping lists alphabetized is important for organized, maintainable code.
Fortunately, Vim has a number of ways to sort lines.

First and foremost, Vim has a built-in sort function. In this example, some
sloppy, inattentive chap has left the Gemfile in utter shambles. We can clean it
up easily.

{% highlight ruby %}
source 'https://rubygems.org'
ruby '2.3.3'

gem 'rails'
gem 'rspec'
gem 'capybara'
gem 'fog'
gem 'poltergeist'
gem 'haml-rails'
gem 'pismo'
{% endhighlight %}

With our cursor on the first _gem_ line, `V` will put us in
visual select mode and `G` will highlight to the end of the file. Then `:sort`
will use Vim's built-in sort capability and we'll end up with a vastly more
tolerable:

{% highlight ruby %}
source 'https://rubygems.org'
ruby '2.3.3'

gem 'capybara'
gem 'fog'
gem 'haml-rails'
gem 'pismo'
gem 'poltergeist'
gem 'rails'
gem 'rspec'
{% endhighlight %}

If we wanted to sort in reverse, then `:sort!` will do the trick. But don't get
that confused with `:!sort`. The `!` command on a block of text executes the
proceeding command in the shell, passing the highlighted text to stdin and
returning the output into Vim. That means `:!sort`, assuming a Unix-like
operating system, will do the same as Vim's built-in `:sort`: alphabetize the
highlighted text from A-Z.

There are [lots of variations](http://vim.wikia.com/wiki/Sort_lines) we can do on
sorts either with the Unix _sort_ utility or Vim's:

Sort and remove duplicate lines, the Vim way and the Unix way:

{% highlight VimL %}
:sort u
:!sort | uniq
{% endhighlight %}

Sort and respect month order by month name:

{% highlight VimL %}
:!sort -M
{% endhighlight %}

Sort numerically:

{% highlight VimL %}
:sort n
{% endhighlight %}

For more options and ideas, check out the docs for Vim's sort with `:help sort`
or _man sort_ for the Unix utility.
