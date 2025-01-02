---
layout: default
title: Sprunki
---

# Welcome to Sprunki Directory

<div class="game-grid">
    {% for game in site.games %}
        <div class="game-tile">
            <a href="{{ game.url }}">
                <img src="{{ site.baseurl }}/assets/games/{{ game.screenshot }}" alt="{{ game.title }}">
                <h3>{{ game.title }}</h3>
            </a>
        </div>
    {% endfor %}
</div>

<style>
    .game-grid {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
        margin-top: 20px;
    }
    .game-tile {
        width: 200px;
        text-align: center;
        background-color: #1e1e1e;
        padding: 10px;
        border-radius: 10px;
        transition: transform 0.2s;
    }
    .game-tile:hover {
        transform: scale(1.05);
    }
    .game-tile img {
        width: 100%;
        height: auto;
        border-radius: 10px;
    }
    .game-tile h3 {
        margin-top: 10px;
        font-size: 1.2em;
    }
</style>
