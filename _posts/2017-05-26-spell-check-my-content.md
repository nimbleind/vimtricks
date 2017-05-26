---
layout: post
title: "Spell Check in Vim!?"
date: 2017-05-26 00:40:00
categories: Essentials
author:
  name: 'Michael Kelly'
  email: 'michaelkelly322@gmail.com'
  url: 'https://thebadmonkeydev.github.io'
  github: thebadmonkeydev
---

Vim can totally spell check. It even goes further than that and
identifies rare and regional words, too! None of this is enabled by default,
however. To enable spell check in Vim just run `:set spell` and suddenly
all misspelled words in your current window will be highlighted (The color and highlight method
will depend on your vim color scheme, mine changes the font color to
dark red and underlines the word).

It's not just a display thing either. Vim provides some very useful
shortcuts for working with spell.

**Navigating Spelling Errors**

- `]s` - Move to the next misspelled word
- `[s` - Move to the next misspelled word backwards
- `]S` - Move to the next misspelled word (skipping rare and regional terms)
- `[S` - Same as `]S` but backwards

**Managing the Dictionary**

_These apply when the cursor is on a word_

- `zg` - Add the word to the "good word list"
- `zG` - Add the word to the internal word list
- `zw` - Mark a word as bad (remove it from the good words list if it
exists there)
- `zW` - Mark a word as bad (remove it from the internal word list if it
exists there)

**Automate All The Things**

If you're anything like me, you write code that has no business seeing
the inside of a spell checker most of the time, but you also write a
whole lot of Markdown and other content that needs spell checking. It
can be tedious enabling/disabling spell as I navigate around these
different tasks. But vim loves automation, right? Just add the following somewhere in your
`.vimrc` file to have vim automagically set spell when you edit a file
it recognizes as markdown:

{% highlight VimL %}

autocmd Filetype markdown setlocal spell

{% endhighlight %}

Now you'll get automatic highlighting of misspelled words when you
actually care to see them.

**TL;DR** Vim has spell check. Run `:set spell` and check it out!
