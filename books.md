---
layout: default
title: Books
permalink: /books/
---

<h1>Books</h1>
<p class="blog-kicker">Nonfiction books I've read, loved, bought to read next, or some combination of the three.</p>

<ul class="book-list">
{% assign books = site.data.books.items | sort: "year" | reverse %}
{% for book in books %}
{% include book.html book=book %}
{% endfor %}
</ul>
