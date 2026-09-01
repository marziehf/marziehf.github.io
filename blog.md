---
layout: default
title: Blog
permalink: /blog/
description: Personal writing on language, meaning, and intelligence.
---

<h1>Blog</h1>
<p class="blog-kicker">whitespace. meaning. and intelligence</p>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="meta">{{ post.date | date: "%B %-d, %Y" }}</p>
      {% if post.description %}<p>{{ post.description }}</p>{% endif %}
    </li>
  {% endfor %}
</ul>
