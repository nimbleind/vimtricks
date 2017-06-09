---
layout: post
title: dispatch rspec single test
date: 2017-06-09 07:37:03
categories: Plugins
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

If you use Tim Pope's [vim-dispatch](https://github.com/tpope/vim-dispatch), you
likely have adopted his setup to use the F9 key to run tests. It's not
uncommon that I wish to invoke a particular test example.

This is possible from the command line for line 32 of some_model.rb

{% highlight plain %}

bundle exec rspec /spec/models/some_moddel.rb:32

{% endhighlight %}

This can be invoked through vim-dispatch like so:

{% highlight plain %}

nnoremap <F8> :execute "Dispatch bundle exec rspec %: . line(".")<CR>

{% endhighlight %}

There are two niceties that can come out of this.

You can focus on a particular test when coding, running only that test.  Once
this test passes, I then switch over to F9 invoking all the tests for the
current file.

Additionally
[pry-byebug](https://github.com/deivid-rodriguez/pry-byebug) can be placed in the
particular example being executed, or anywhere in the code path being tested
for that matter.  This allows for quick, repetitive debugging/investigating.
