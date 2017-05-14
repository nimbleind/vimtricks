---
layout: page
title: Vim Tricks Archive
permalink: /archive/
banner_image: sample-banner-image-3.jpg
---

<div>
  <ul>
    {% for post in site.posts %}
      <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
