---
layout: default
title: Papers
permalink: /papers/
---

<h1>Papers</h1>
<p class="filter-note">
A most likely incomplete list of papers, find the full list on
<a href="https://scholar.google.com/citations?hl=en&user=NZqs0toAAAAJ&view_op=list_works&sortby=pubdate">Google Scholar</a>.
</p>

<div class="pub-tabs" role="tablist">
<!-- <button class="pub-tab active" type="button" role="tab" aria-selected="true" data-target="tab-selected">Selected</button> -->
{% for topic in site.data.topics %}
<button class="pub-tab" type="button" role="tab" aria-selected="false" data-target="tab-{{ topic.id }}">{{ topic.label }}</button>
{% endfor %}
<button class="pub-tab active" type="button" role="tab" aria-selected="true" data-target="tab-all">All</button>
</div>

<!-- <div class="pub-list pub-section is-active" id="tab-selected">
{% assign selected_by_year = site.data.papers | where: "selected", true | group_by: "year" | sort: "name" | reverse %}
{% for year_group in selected_by_year %}
{% for paper in year_group.items %}
{% include paper.html paper=paper %}
{% endfor %}
{% endfor %}
</div> -->

{% for topic in site.data.topics %}
<div class="pub-list pub-section" id="tab-{{ topic.id }}">
{% assign tagged = site.data.papers | where_exp: "p", "p.topics contains topic.id" %}
{% assign tagged_by_year = tagged | group_by: "year" | sort: "name" | reverse %}
{% for year_group in tagged_by_year %}
{% for paper in year_group.items %}
{% include paper.html paper=paper %}
{% endfor %}
{% endfor %}
</div>
{% endfor %}

<div class="pub-list pub-section is-active" id="tab-all">
{% assign papers_by_year = site.data.papers | group_by: "year" | sort: "name" | reverse %}
{% for year_group in papers_by_year %}
{% for paper in year_group.items %}
{% include paper.html paper=paper %}
{% endfor %}
{% endfor %}
</div>

<script>
(function () {
  var tabs = document.querySelectorAll(".pub-tab");
  var sections = document.querySelectorAll(".pub-section");
  function show(id) {
    var found = false;
    tabs.forEach(function (tab) {
      var on = tab.getAttribute("data-target") === id;
      tab.classList.toggle("active", on);
      tab.setAttribute("aria-selected", on ? "true" : "false");
      if (on) found = true;
    });
    if (!found) return show("tab-all");
    sections.forEach(function (section) {
      section.classList.toggle("is-active", section.id === id);
    });
  }
  tabs.forEach(function (tab) {
    tab.addEventListener("click", function () {
      var id = tab.getAttribute("data-target");
      show(id);
      if (history.replaceState) history.replaceState(null, "", "?tab=" + id);
    });
  });
  show(new URLSearchParams(location.search).get("tab") || "tab-all");
})();
</script>
