---
layout: default
title: Mentorship
permalink: /mentorship/
description: Mentorship, supervision, teaching, and service.
wide: true
---

<h1>Mentorship</h1>
<p class="mentorship-intro">{{ site.data.mentorship.intro }}</p>

<div class="mentee-grid">
{% for s in site.data.mentorship.supervision %}
<div class="mentee-card">
<div class="mentee-avatar"><span class="mentee-initials">{{ s.initials }}</span></div>
<div>
<div class="mentee-name">{{ s.name }}</div>
<div class="mentee-track">{{ s.role }} ({{ s.year }})</div>
{% if s.topic %}<div class="mentee-dest">{{ s.topic }}</div>{% endif %}
</div>
</div>
{% endfor %}
</div>

<h2 class="section-label">Mentorship</h2>
<ul class="quiet-list">
{% for p in site.data.mentorship.programs %}
<li>{{ p }}</li>
{% endfor %}
</ul>

<h2 class="section-label">Program committee</h2>
<ul class="quiet-list">
{% for s in site.data.mentorship.service %}
<li>{{ s }}</li>
{% endfor %}
</ul>

<h2 class="section-label">Teaching</h2>
<ul class="quiet-list">
{% for t in site.data.mentorship.teaching %}
<li><span class="quiet-year">{{ t.year }}</span> {{ t.course }} — {{ t.where }}</li>
{% endfor %}
</ul>
