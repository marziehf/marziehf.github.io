---
layout: default
title: About
permalink: /
wide: true
---

<header class="hero">
  <img class="hero-photo" src="{{ site.author.photo | relative_url }}" alt="{{ site.author.name }}" width="300" height="400">
  <h1>{{ site.author.name }}</h1>
  <p class="role"><strong>{{ site.author.role }}</strong> @ <a href="{{ site.author.org_url }}">{{ site.author.org }}</a></p>
  {% include socials.html %}
  <div class="bio">
    <p>
    I lead <a href="https://cohere.com/research">Cohere Labs</a>, where we work on making AI systems
    <strong>trustworthy, collaborative, and globally inclusive</strong>. My research spans multilingual
    and culturally adaptive models, data-efficient learning, and evaluation methods for understanding
    how AI systems behave and affect people in the real world. At Cohere Labs, I have worked closely with <a href="https://www.sarahooker.me/">Sara Hooker</a>
    and <a href="https://scholar.google.com/citations?user=CEt6_mMAAAAJ&hl=en">Joelle Pineau</a>
    on open, trustworthy, and globally relevant AI research. I received my PhD from the University
    of Amsterdam, advised by <a href="https://staff.fnwi.uva.nl/c.monz/index.html">Christof Monz</a>
    and <a href="http://www.cs.rug.nl/~bisazza/index.html">Arianna Bisazza</a>.
  </p>

  <p>
    More broadly I'm interested in the <strong>creative and expressive sides of intelligence</strong>:
    how knowledge changes as it moves between languages, cultures, representations, and modes of
    understanding. On my free time I like to think about how we can build systems that learn, communicate,
    and generalize across the diversity of human experience.
  </p>
  </div>
</header>

<!-- <h2 class="section-label">Research highlights</h2>
<div class="highlights">
  {% for h in site.data.highlights %}
  <details class="highlight">
    <summary>
      <h3>{{ h.title }}</h3>
      <p class="lede">{{ h.summary }}</p>
      <span class="explore">Explore →</span>
    </summary>
    <div class="highlight-body">
      <p>{{ h.body }}</p>
      <ul>
        {% for pid in h.papers %}
          {% assign p = site.data.papers | where: "id", pid | first %}
          {% if p %}
            <li>
              {% if p.links.pdf %}<a href="{{ p.links.pdf }}">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}
              <span>({{ p.venue }} {{ p.year }})</span>
            </li>
          {% endif %}
        {% endfor %}
      </ul>
    </div>
  </details>
  {% endfor %}
</div> -->
