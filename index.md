---
layout: home
title: Sprunki
---
# Welcome to Sprunki Directory

This is a static site for Sprunki games

<ul>
  {% for game in site.games %}
    <li>
      <a href="{{ game.url }}">{{ game.title }}</a>
    </li>
  {% endfor %}
</ul>
