---
layout: post
title: paste from register in command
date: 2018 Nov 01 07:09:25
categories: Essentials
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

Occasionally I'd like to use some portion of contents from a buffer/ file in a
vim command.  Copying and pasting with a mouse/ touchpad is is a flow killer for
me. There's a way to paste the contents of a vim register in the vim command
window.  Using `<C-r>` in command mode will interpret the next character(s)
as a register and insert the contents of the register into the vim command!

A common use for this is to search for an entire string literal using `Ggrep`:


{% highlight plain %}
  def is_active?
    status == 'sales active'
  end
{% endhighlight %}

If I would like to search for the literal 'sales active', I would first
place my cursor within the quoted string and type `ya'` to yank to
around the string literal into the unnamed vim register.  From there
I'd hit ESC to go to command mode, and type `Ggrep`, followed by `<C-r>`
followed by a vim register.  In this case the double quote `"` is vim's
unnamed register.

{% highlight plain %}
:Ggrep <C-r>"
{% endhighlight %}

The `<C-r>` will be replaced with the contents of the unnamed register
like so:

{% highlight plain %}
:Ggrep 'sales active'
{% endhighlight %}

Interestingly, `<C-r>` works in insert or append mode in a buffer
as well!



