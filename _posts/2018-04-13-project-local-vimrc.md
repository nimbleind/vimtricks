---
layout: post
title: 2018 04 13 project local vimrc
date: 2018-04-13 14:53:44
categories: Essentials
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

I recently began freelancing again, which means working on many different
projects.  Diverse projects bring diverse needs with respect to vim
configuration.  For example commands to fire off tests can vary based on
testing framework or file system layout.

I recently found that vim can look in your current directory at start time
for a .vimrc.  This file will be processed after the main .vimrc is processed.

To turn on this feature place the following in your main .vimrc:

{% highlight plain %}

set exrc
set secure

{% endhighlight %}

When using exrc, it's recommended to use secure.  When secure is set, any vimrc
file which is not owned by the owner of the vim process has certain limitations
applied.  These include :autocmd, shell and write command limitations.

Note, while this is not a vim specific recommendation, I also did not want to
leak .vimrc into project/ customer .gitignore files.  So I place .vimrc in
my .git/info/exclude - which allows for application of rules like .gitignore but
is never checked in/ tracked by git.

