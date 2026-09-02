---
layout: default
title: Books
permalink: /books/
---

<h1>Books</h1>
<p class="blog-kicker">Books [non-fiction] I keep coming back to in order of when they came to life.</p>

<ul class="book-list">
{% assign books = site.data.books.items | sort: "year" | reverse %}
{% for book in books %}
{% include book.html book=book %}
{% endfor %}
</ul>
