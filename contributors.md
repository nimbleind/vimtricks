---
layout: page
title: Contributors
permalink: /contributors/
---

{% assign authors = site.posts | map: 'author' | uniq | sort: 'name' %}

{% for author in authors %}* [{{author.name}}]({{author.url}})
{% endfor %}

Want to contribute a Vim Trick? [Fork our repo](https://github.com/cbartlett/vimtricks).
