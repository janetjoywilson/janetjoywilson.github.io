---
layout: page
title: Library Catalogs
description: "The Library cataloged by type of book"
permalink: /library/catalog/
---

<ul class="categories">
  <li><a href="{{ site.url }}/library/">All</a></li>
  {% for category in site.data.categories %}
  <li><a href="{{ site.url }}/library/catalog/#{{ category }}">{{ category }}</a></li>
  {% unless forloop.last %}
  {% endunless %}
  {% endfor %}
</ul>

{% for category in site.data.categories %}
<h2 id="{{ category }}"><a href="#{{ category }}">{{ category }}</a></h2>
<ul class="book-list">
{% for book in site.library %}
{% if book.categories contains category %}
  <li>
    <a href="{{ site.url }}{{ book.url }}">
      <img src="{{ site.url }}/images/covers/{{ book.image }}" />
      <h4>{{ book.title }}</h4>
      <br />
      <h6>{{ book.author }}</h6>
    </a>
  </li>
{% endif %}
{% endfor %}
</ul>

{% endfor %}
