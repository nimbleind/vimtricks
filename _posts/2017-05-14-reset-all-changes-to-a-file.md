---
layout: post
title: Reset all changes to a file
date: 2017-05-14 07:43:55
categories: Plugins Git
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Using [tpope](http://tpo.pe/)'s [Fugitive](https://github.com/tpope/vim-fugitive) plugin, you can easily reset a file back to it's checked-in state with `:Gread`.

All of the changes to your file since the last _git add_ or _git checkout_ will be cleared and the last checked-in version will load into the buffer. You can then `:w` to write the file back to disk.
