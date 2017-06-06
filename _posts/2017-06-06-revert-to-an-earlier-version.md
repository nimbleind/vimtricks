---
layout: post
title: Revert to an earlier version
date: 2017-06-06 07:00:00
categories: Essentials
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

You're probably already familiar with `u` and `Ctrl-r` to undo and redo changes in Vim. But did you know Vim has a built in time machine?

Using `:earlier 1m` you can go back to an earlier version of your file. Vim will roll back through your text states to the referenced time. You can use _n_ seconds `s`, minutes `m`, hours `h`, or even days `d`.

And there is a corresponding `:later` command to move back forward in time through the history.

Here's the full text on `:earlier` and `:later`, retrieved from `:help undo`:

{% highlight text %}
:earlier {count}  Go to older text state {count} times.
:earlier {N}s   Go to older text state about {N} seconds before.
:earlier {N}m   Go to older text state about {N} minutes before.
:earlier {N}h   Go to older text state about {N} hours before.
:earlier {N}d   Go to older text state about {N} days before.

:earlier {N}f   Go to older text state {N} file writes before.
      When changes were made since the last write
      ":earlier 1f" will revert the text to the state when
      it was written.  Otherwise it will go to the write
      before that.
      When at the state of the first file write, or when
      the file was not written, ":earlier 1f" will go to
      before the first change.

:later {count}    Go to newer text state {count} times.
:later {N}s   Go to newer text state about {N} seconds later.
:later {N}m   Go to newer text state about {N} minutes later.
:later {N}h   Go to newer text state about {N} hours later.
:later {N}d   Go to newer text state about {N} days later.

:later {N}f   Go to newer text state {N} file writes later.
      When at the state of the last file write, ":later 1f"
      will go to the newest text state.
{% endhighlight %}
