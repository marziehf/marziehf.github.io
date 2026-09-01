---
layout: default
title: Papers
permalink: /papers/
---

<h1>Papers</h1>

<p class="filter-note">
  Selected research. See my full publication list on
  <a href="https://scholar.google.com/citations?hl=en&user=NZqs0toAAAAJ&view_op=list_works&sortby=pubdate">
    Google Scholar.
  </a>
</p>

<!-- <h2 class="section-label">Selected</h2>
<p class="filter-note">A few papers that best represent my current research. The full list is below.</p>
{% assign selected = site.data.papers | where: "selected", true %}
{% for paper in selected %}
  {% include paper.html paper=paper %}
{% endfor %} -->

{% assign papers_by_year = site.data.papers | group_by: "year" | sort: "name" | reverse %}
{% for year_group in papers_by_year %}
<div class="paper-year-group">
<h2 class="paper-year">{{ year_group.name }}</h2>
{% for paper in year_group.items %}
{% include paper.html paper=paper %}
{% endfor %}
</div>
{% endfor %}
