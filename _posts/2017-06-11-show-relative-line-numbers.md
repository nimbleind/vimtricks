---
layout: post
title: Show relative line numbers
date: 2017-06-11 07:00:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Many operations in Vim can be executed over a given number of lines. For
example, `d3j` will delete the current line, plus the 3 below it. You may
find yourself reading the line numbers and then subtracting two numbers
in your head to decide how many lines to execute a command over. But
there is a better way.

Vim allows the line numbers to show relative to current cursor position
with `:set relativenumber`. Here's a short demonstration:

<asciinema-player src="/assets/screencasts/relative.json"></asciinema-player>
