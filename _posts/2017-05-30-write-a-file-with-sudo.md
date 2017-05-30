---
layout: post
title: Write a file with sudo
date: 2017-05-30 07:39:00
categories: Essentials Plugins
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Ever open your _/etc/hosts_ file in Vim, make a bunch of edits, only to `:wq` and
get that dreaded read only error? There a few easy ways to sudo write a
privileged file in Vim.

When Vim can't write to a file because it wasn't opened as sudo, this is the
ominous message you'll see:

{% highlight plain %}
E45: 'readonly' option is set (add ! to override)
{% endhighlight %}

Ordinarily you might `:q!` then reopen the file with _sudo vim /etc/hosts_,
entering your password when prompted. But then you've lost your changes. If you
have [tpope](http://tpo.pe/)'s [eunuch.vim](https://github.com/tpope/vim-eunuch) plugin, you have
an easy option with:

{% highlight VimL %}
:SudoWrite
{% endhighlight %}

This will prompt you for your sudo password and write the file.

If you prefer a native Vim method, you can combine some features of Vim and the
Unix _tee_ utility to the same effect:

{% highlight VimL %}
:w !sudo tee %
{% endhighlight %}

This will also prompt you for your sudo password and write the file. But how
does it work?

Vim allows you to write the current buffer while piping it
through a command with the `:w !command` syntax. And Vim allows the use of the
`%` character as a substitution for the current buffer's full file path and
name. Therefore, the write is piped through the resulting command _sudo tee
/etc/hosts_. Unix _tee_ utility is used which reads from stdin and writes to
stdout along with the specified file. Since _tee_ was invoked with sudo
privileges, it can write the to file while Vim cannot.

Arguably, `:SudoWrite` is easier to remember and eunuch.vim includes a bunch of
other useful Unix utilities, so unless you're a purist, download and install [eunuch.vim](https://github.com/tpope/vim-eunuch).
