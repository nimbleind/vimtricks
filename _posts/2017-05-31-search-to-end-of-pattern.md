---
layout: post
title: Search positioning
date: 2017-05-31 08:49:37
categories: Essentials
author:
  name: 'Andrew Libby'
  email: 'alibby@andylibby.org'
  url: 'https://github.com/alibby'
  github: alibby
---

When searching with `/pattern` in vim, the cursor lands at the start of the
pattern.  This is not always ideal. By adding `/e` to the end of your search
pattern, you can have the cursor land at the end of the search pattern.  This
can come in handy when you would like to cycle through a number of instance of
a search pattern and repeat an edit with the dot operator `.`.

Consider the following where you'd like to remove a parameter from multiple
method calls:

{% highlight plain %}

some_method(param1, param2, param3)
some_method(param1, param2, some_other)
some_method(param1, param2, another_yet)
some_method(param1, param2, and_so_on)

{% endhighlight %}

Executing a search `/param2,/e` will land you on the comma after param2.  Then
executing `dt)` will delete up to the _)_ character. Using `n` followed by `.`
will skip to the next occurrence of _param2,_, and the dot will repeat the
previous delete to right praren.  A few repeats of `n` followed by `.` and our
work is finished:

{% highlight plain %}

some_method(param1, param2)
some_method(param1, param2)
some_method(param1, param2)
some_method(param1, param2)

{% endhighlight %}

Not surprisingly, there are a number of search modifiers that will impact cursor
positioning.  The following excerpt from `:help search-offset`:

{% highlight plain %}
The offset gives the cursor position relative to the found match:
    [num]	[num] lines downwards, in column 1
    +[num]	[num] lines downwards, in column 1
    -[num]	[num] lines upwards, in column 1
    e[+num]	[num] characters to the right of the end of the match
    e[-num]	[num] characters to the left of the end of the match
    s[+num]	[num] characters to the right of the start of the match
    s[-num]	[num] characters to the left of the start of the match
    b[+num]	[num] identical to s[+num] above (mnemonic: begin)
    b[-num]	[num] identical to s[-num] above (mnemonic: begin)
    ;{pattern}  perform another search, see |//;|

If a '-' or '+' is given but [num] is omitted, a count of one will be used.
When including an offset with 'e', the search becomes inclusive (the
character the cursor lands on is included in operations).

Examples:

pattern			cursor position	~
/test/+1		one line below "test", in column 1
/test/e			on the last t of "test"
/test/s+2		on the 's' of "test"
/test/b-3		three characters before "test"

{% endhighlight %}

Happy searching!

