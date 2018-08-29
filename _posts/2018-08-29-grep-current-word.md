---
layout: post
title: grep current word
date: 2018 Aug 29 10:09:57
categories: Essentials
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

While pairing a coworker remarked that I'm able to jump around in vim quite
quickly. While I use a number of techniques to jump around, including
[gf](http://vim.wikia.com/wiki/Open_file_under_cursor),
[rails-vim](https://github.com/tpope/vim-rails) A, R and their family. I
came up with a variation on the ever handy `*`.  Using the star
will jump to the next occurrence of the word under the cursor.  This jump
jump is limited to the current file.  I thought it might be handy to 
have a leader command to quickly be able to
[Ggrep](https://github.com/tpope/vim-fugitive) for `<cword>` (the word
under the cursor).

{% highlight plain %}

map <leader>* :Ggrep <cword><CR><CR>

{% endhighlight %}

The above in my `.vimrc` allows me to hit leader star to Ggrep for the word
under the cursor. Ggrep, in all of it's awesomeness uses the quickfix window for
results. Quickfix navigation options like :cnext and :cprev can be used.  I use
the [unimpaired](https://github.com/tpope/vim-unimpaired) plugin provides `]q` and
`[q` to traverse through the list of hits.

I hope this trick proves to be as useful for others as it has for
myself.


