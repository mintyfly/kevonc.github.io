---
layout: page
title: "kevon's blog | life and code"
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts limit: 5 %}
    <li class="post">
      <h4 class="title"><a href="{{ post.url }}">{{ post.title }}</a></h4>
      <span class="date">{{ post.date | date: "%B %-d, %Y" }}</span>
      <span class="excerpt">{{ post.excerpt }}</span>
    </li>
  {% endfor %}
</ul>

<div class="more"><a href="{{ BASE_PATH }}{{ site.JB.archive_path }}">See More</a></div>