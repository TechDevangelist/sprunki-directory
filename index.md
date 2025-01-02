# main index.md
---
layout: home
title: Sprunki
---
# Welcome to Sprunki Directory
This is a static site for Sprunki games

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>