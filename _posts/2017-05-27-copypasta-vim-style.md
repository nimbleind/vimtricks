---
layout: post
title: "Copy/Pasta Vim Style"
date: 2017-05-27 00:00:00
categories: Essentials
author:
  name: 'Michael Kelly'
  email: 'michaelkelly322@gmail.com'
  url: 'https://thebadmonkeydev.github.io'
  github: thebadmonkeydev
---

At this point in the technology age, nothing is more powerful and
necessary to anyone editing text than being able to copy and paste.
Here's how to do it Vim style:

**Copying and Cutting**
Vim calls "copy" "yank" so all the shortcuts for yanking text are based
around, surprise surprise, `y`. In any visual mode, select the text you
want to yank and just hit `y`...it really is that simple.

There are some pretty powerful variations on this shortcut in normal mode:

- `yy` - yank entire line
- `yj` - yank current line and line below
- `yk` - yank current line and line above
- `yw` - yank from the cursor to the end of the word
- `y$` - yank from the cursor to the end of the line
- `y0` - yank from the cursor back to the beginning of the line
- `yiw` - yank the word under the cursor
- `yaw` - yank the word under the cursor including surrounding
whitespace

Vim basically cuts every time you delete something using either `d` or
`x`. Both shortcuts will move the deleted text to the default register
(just like yank) before deleting it.  `d` can be substituted for `y` in
all of the above commands.

**Pasting**
After you have _yanked_ or _deleted_ some text, you can paste it by
pressing `p` in normal mode. This will place all text in the default
register after the cursor. You can paste the contents before the cursors
current location with `P`.

**TL;DR** Copy with `y`, cut with `d`, paste with `p`
