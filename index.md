---
layout: page
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts limit: 5 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <p>{{ post.date | date_to_long_string }}</p>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>
