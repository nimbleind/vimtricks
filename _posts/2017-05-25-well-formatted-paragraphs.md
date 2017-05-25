---
layout: post
title: Well Formatted Paragraphs
date: 2017-05-25 09:05:00
categories: Essentials
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: https://github.com/alibby'
  github: alibby
---

Many folks use vim for software development or systems administration but
choose other editors when editing plain text or markdown.  Vim has some pretty
handy features for dealing with prose.  

When authoring prose there I use textwidth to automatically wrap lines at a
reasonable length.  In my .vimrc:

{% highlight VimL %}

set textwidth=80

{% endhighlight %}

This not only help keep paragraphs sensible when authoring prose, it also
reminds me to keep source code lines sensibly short by wrapping when they wind
up too long.  textwidth

Automatic line wrapping provided by textwidth is handy when writing, but it
tends to come apart when editing.  In order to re-format text after editing has
left formatting untidy, we can use `gq`.  The `gq` command reformats based on a
motion or a visual selection.  

To demonstrate, note the following short lines of ipsum:

{% highlight HTML %}
Lorem ipsum dolor sit amet,
consectetur adipiscing elit. Praesent aliquam
rhoncus mattis. Phasellus
a lacinia enim. Duis quis semper neque. Sed
sollicitudin volutpat
dui, ut imperdiet velit lacinia vel.
{% endhighlight %}

Executing gq after selecting all lines visually (`ggvGgq`) results in the
following

{% highlight HTML %}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent aliquam
rhoncus mattis. Phasellus a lacinia enim. Duis quis semper neque. Sed
sollicitudin volutpat dui, ut imperdiet velit lacinia vel.
{% endhighlight %}

Happy authoring!



  
