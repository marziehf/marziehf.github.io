---
layout: default
title: Press
permalink: /in-the-news/
description: Selected press and media coverage.
---

<h1>Press coverage of our works</h1>

{% assign press_by_year = site.data.press | group_by_exp: "item", "item.date | date: '%Y'" | sort: "name" | reverse %}
{% for year_group in press_by_year %}
<div class="paper-year-group">
<ul class="press-list">
{% for item in year_group.items %}
<p class="press-meta">{{ item.date | date: "%b %d, %Y" }} · {{ item.outlet }}</p>
<a href="{{ item.url }}">{{ item.title }}</a>
{% endfor %}
{% endfor %}
