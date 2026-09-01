---
layout: default
title: Talks
permalink: /talks/
description: Invited talks, keynotes, and panels.
---

<h1>Talks</h1>

<details class="bio-box">
<summary>Short bio for speaking engagements</summary>
<p>{{ site.data.talks.speaker_bio }}</p>
</details>

{% assign upcoming = site.data.talks.items | where: "upcoming", true %}
{% if upcoming.size > 0 %}
<div class="timeline-year-group">
<h2 class="timeline-year">Upcoming</h2>
<div class="timeline">
{% for t in upcoming %}
{% include talk.html talk=t %}
{% endfor %}
</div>
</div>
{% endif %}

{% assign years = "2026,2025,2024,2023,2022,2021,2020,2018" | split: "," %}
{% for y in years %}
{% assign yint = y | plus: 0 %}
{% assign group = site.data.talks.items | where: "year", yint | where: "upcoming", false %}
{% if group.size > 0 %}
<div class="timeline-year-group">
<h2 class="timeline-year">{{ y }}</h2>
<div class="timeline">
{% for t in group %}
{% include talk.html talk=t %}
{% endfor %}
</div>
</div>
{% endif %}
{% endfor %}
