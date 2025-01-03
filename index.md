---
layout: default
title: Sprunki
---

# Welcome to Sprunki Directory

<div class="game-grid">
    {% for game in site.games %}
        <div class="game-tile" onclick="openModal('{{ game.iframe_url }}')">
            <img src="{{ site.baseurl }}{{ game.screenshot }}" alt="{{ game.title }}">
            <h3>{{ game.title }}</h3>
        </div>
    {% endfor %}
</div>

<div id="modal" class="modal">
    <div class="modal-content">
        <span class="close" onclick="closeModal()">&times;</span>
        <iframe id="modal-iframe" src="" frameborder="0"></iframe>
    </div>
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
        cursor: pointer;
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
    .modal {
        display: none;
        position: fixed;
        z-index: 1000;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.8);
        justify-content: center;
        align-items: center;
    }
    .modal-content {
        position: relative;
        background-color: #121212;
        padding: 20px;
        border-radius: 10px;
        width: 90%;
        height: 90%;
        max-width: 1200px;
        max-height: 800px;
        margin: 20px;
    }
    .close {
        position: absolute;
        top: 10px;
        right: 10px;
        color: #fff;
        font-size: 36px;
        font-weight: bold;
        cursor: pointer;
        padding: 10px;
        z-index: 1001;
    }

    .close:hover {
        color: #ccc;
    }

    .modal-content {
        position: relative;
        background-color: #121212;
        padding: 40px;
        border-radius: 10px;
        width: 90%;
        height: 90%;
        max-width: 1200px;
        max-height: 800px;
        margin: 20px;
        touch-action: manipulation;
    }
    iframe {
        width: 100%;
        height: 100%;
        border: none;
        border-radius: 10px;
    }
</style>

<script>
    function openModal(iframeUrl) {
        const modal = document.getElementById('modal');
        const iframe = document.getElementById('modal-iframe');
        iframe.src = iframeUrl;
        modal.style.display = 'flex';
    }

    function closeModal() {
        const modal = document.getElementById('modal');
        const iframe = document.getElementById('modal-iframe');
        iframe.src = '';
        modal.style.display = 'none';
    }

    // Handle both mouse and touch events
function handleModalClose(event) {
    const modal = document.getElementById('modal');
    if (event.target === modal) {
        closeModal();
    }
}

window.addEventListener('click', handleModalClose);
window.addEventListener('touchend', handleModalClose);

// Prevent iframe from swallowing touch events
document.getElementById('modal-iframe').addEventListener('touchstart', function(e) {
    e.stopPropagation();
});
</script>
