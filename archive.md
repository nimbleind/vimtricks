---
layout: page
title: Vim Tricks Archive
permalink: /archive/
banner_image: vim.jpg
---

<div>
  <ul>
    {% for post in site.posts %}
      <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
