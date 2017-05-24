---
layout: post
title: Change case
date: 2017-05-24 07:02:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

There are numerous ways to manipulate the case of text in Vim. The most important commands to remember are:

* `~` toggles case: from lower to UPPER or from UPPER to lower
* `u` lowercases
* `U` uppercases

These must be combined with various Vim movements and selection mechanisms. For example, here are some of the most used and mose useful case changes for programmers in vim:

* `~` Toggle case of the character under the cursor
* `V~` Toggle case of entire line (Shift-v will visually select the current line, then `~` will toggle the case.)
* `g~w` Toggle case from cursor to end of word
* `g~iw` Toggle case of entire word (Works even when in the middle of a word.)

Of course the possibilities are endless:

* `gUw` Uppercase from cursor to end of word
* `guw` Lowercase from cursor to end of word
* `g~w` Toggle case from cursor to end of word
* `guG` Lowercase to end of file
* `gUG` Uppercase to end of file
* `g~G` Toggle case to end of file
* `gu$` Lowercase to end of current line
* `gU$` Uppercase to end of current line
* `g~$` Toggle case to end of current line
* `gu^` Lowercase to beginning of current line
* `gU^` Uppercase to beginning of current line
* `g~^` Toggle case to beginning of current line
* `ggVGu` Lowercase entire file (Goes to the top, visually selects, goes to the bottom, lowercases)
* `ggVGU` Uppercase entire file
* `ggVG~` Toggle case entire file
