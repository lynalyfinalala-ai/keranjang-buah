<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Catch The Fruit</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background: #0f172a; color: #f8fafc; display: flex; flex-direction: column; align-items: center; justify-content: center; min-height: 100vh; overflow: hidden; }
        .game-container { position: relative; width: 100%; max-width: 480px; height: 640px; background: linear-gradient(to bottom, #1e293b, #0f172a); border-radius: 16px; overflow: hidden; box-shadow: 0 10px 25px rgba(0,0,0,0.5); border: 2px solid #334155; }
        canvas { display: block; width: 100%; height: 100%; }
        .ui-overlay { position: absolute; top: 0; left: 0; width: 100%; padding: 16px; display: flex; justify-content: space-between; align-items: center; pointer-events: none; font-weight: bold; font-size: 1.1rem; text-shadow: 0 2px 4px rgba(0,0,0,0.5); }
        .screen { position: absolute; inset: 0; background: rgba(15, 23, 42, 0.9); display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; padding: 24px; z-index: 10; transition: opacity 0.3s ease; }
        .screen.hidden { opacity: 0; pointer-events: none; }
        h1 { font-size: 2.2rem; margin-bottom: 8px; color: #38bdf8; }
        p { color: #94a3b8; margin-bottom: 24px; font-size: 0.95rem; line-height: 1.5; }
        .btn { background: #0284c7; color: white; border: none; padding: 12px 28px; font-size: 1rem; font-weight: bold; border-radius: 8px; cursor: pointer; transition: background 0.2s, transform 0.1s; box-shadow: 0 4px 12px rgba(2, 132, 199, 0.4); }
        .btn:hover { background: #0369a1; transform: translateY(-2px); }
        .btn:active { transform: translateY(0); }
        .controls-hint { margin-top: 12px; font-size: 0.8rem; color: #64748b; }
    </style>
</head>
<body>

    <div class="game-container">
        <!-- UI Skor & Nyawa -->
        <div class="ui-overlay">
            <div id="scoreDisplay">Skor: 0</div>
            <div id="livesDisplay">❤️ ❤️ ❤️</div>
        </div>

        <!-- Canvas Game -->
        <canvas id="gameCanvas" width="480" height="640"></canvas>

        <!-- Menu Utama -->
        <div id="startScreen" class="screen">
            <h1>Catch The Fruit</h1>
            <p>Tangkap buah-buahan segar ke dalam keranjang. Hindari batu dan bom, atau nyawa melayang!</p>
            <button class="btn" onclick="startGame()">Mulai Main</button>
            <div class="controls-hint">Gunakan Tombol Panah, Geser Layar, atau Mouse</div>
        </div>

        <!-- Menu Game Over -->
        <div id="gameOverScreen" class="screen hidden">
            <h1>Game Over</h1>
            <p id="finalScoreText">Skor Kamu: 0</p>
            <button class="btn" onclick="startGame()">Main Lagi</button>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');

        const startScreen = document.getElementById('startScreen');
        const gameOverScreen = document.getElementById('gameOverScreen');
        const scoreDisplay = document.getElementById('scoreDisplay');
        const livesDisplay = document.getElementById('livesDisplay');
        const finalScoreText = document.getElementById('finalScoreText');

        let score = 0;
        let lives = 3;
        let gameRunning = false;
        let items = [];
        let particles = [];
        let spawnTimer = 0;

        // Karakter Keranjang
        const basket = {
            x: canvas.width / 2 - 40,
            y: canvas.height - 70,
            width: 80,
            height: 40,
            speed: 8,
            dx: 0
        };

        // Daftar Item (Buah & Non-Buah)
        const itemTypes = [
            { name: '🍎', type: 'fruit', points: 10, color: '#ef4444' },
            { name: '🍌', type: 'fruit', points: 15, color: '#eab308' },
