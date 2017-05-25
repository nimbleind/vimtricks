---
layout: post
title: Opening the previous buffer
date: 2017-05-25 00:40:00
categories: Essentials
author:
  name: 'Michael Kelly'
  email: 'michaelkelly322@gmail.com'
  url: 'https://thebadmonkeydev.github.io'
  github: thebadmonkeydev
---

Have you ever accidentally opened a file you didn't intend to from
somewhere like the quick fix window? Or dive deep into debugging a
problem only to realize you need to fix something in one of those files
somehwere in your wake? Then Vim "jumps" are for you!

Everytime you jump to a different location or file in Vim, it records
the file, line, and column you were on when the jump occured. To see
a list of your jumps you can use `:jumps` which will output a list like
this:

```
 jump line  col file/text
  12     8    0 ~/dot.minatrix
  11     1    0 ~/dot.minatrix/bash/helpers.bash
  10     5    0 ~/dot.minatrix/bash/helpers.bash
   9     8    0 ~/projects/thebadmonkeydev/vimtricks
   8     1    0 NERD_tree_1
   7    33    2 NERD_tree_1
   6    19    0 NERD_tree_1
   5     1    0 ---
   4    24   17 list with `:jumps`. Running `:jumps` right now while
   3    46    0 >
   2    35    2 ~/dot.minatrix/bash/bashrc.common.symlink
   1     1    0 _site/index.html
>  0    25    2 produces this list:
   1    53   11 Rakefile
```
_Note that jump locations within your current file show the contents of
the line as apposed to the filename_

Now the fun part! In the list the `>` character indicates which location
in the list you have open. You can navigate back and forth within the jumps list
using

1. `ctrl-o` - moves you upwards in the jumps list
2. `ctrl-i` - moves you downwards in the jumps list

In the example list above, `ctrl-o` would open up the file
`_site/index.html` at line 1 column 0. `ctrl-i` would open the file
`Rakefile` at line 53 column 11.

**TL;DR** `ctrl-o` and `ctrl-i` move forward and backward through vim
jumps and the jumps list can be viewed with `:jumps`
