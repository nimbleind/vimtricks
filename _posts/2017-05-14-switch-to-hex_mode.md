---
layout: post
title: Switch to hex mode
date: 2017-05-14 19:43:55
categories: CIA
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

This trick comes courtesy the CIA, via [WikiLeaks](https://wikileaks.org/ciav7p1/cms/page_3375350.html). This leaked document shows how one can view a binary file in hex mode using the Linux _xxd_ command.

Here's the exact leaked vim trick:

### Switch to a quick Hex mode (Linux)

Editing a binary file ends up looking something like this in Vim:

{% highlight text %}

^B-^@^@^E^X^@^@�^@^M^@^[[38;5;4m^@^@^C^\^?^U^D��^@^Q^S^Z^Y^R^O^W^V^@^@^@^@0^@l^A^@^@^@^@^B-^@^@^E

^@^@^@�^@^M^@^[~J^@^@^C^\^?^U^D��^@^Q^S^Z^Y^R^O^W^V^@^@^@^@^B-^@^@^E^X^@^@�^@^M^@^[~J\^?^U^D��^@

^Q^S^Z^Y^R^O^W^V^@^@^@^@^B-^@^@^E^@^@^@�^@^M^@^[~J^@^@^C^\^?^U^D��^@^Q^S^Z^Y^R^O^W^V^@^@

^@^@^B-^@^@^E^X^@^@�^@^M^@^[~J^@^@^C^\^?^U^D��^@^Q^S^Z^Y^R^O^W^V^@^@^@^@^B-^@^@^E^@
{% endhighlight %}

Type the following to run the buffer through the xxd hex dump command on Linux:

`:%!xxd`

The buffer will change to the following:

{% highlight text %}
0000000: 022d 0000 0518 0000 bd00 0d00 1bca 0000 .-.............. 
0000010: 031c 7f15 04ff ff00 1113 1a19 120f 1716 ................ 
0000020: 0000 0000 3000 6c01 0000 0000 022d 0000 ....0.l......-.. 
0000030: 0500 0000 bd00 0d00 1b8a 0000 031c 7f15 ................
{% endhighlight %}

This is not a true hex editor!  Only changes in the hex columns will carry through a restore!

Restore the original with the following:

`:%!xxd -r`
