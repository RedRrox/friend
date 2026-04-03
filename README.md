<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends Collection</title>
    <link rel="icon" type="image/jpeg" href="rrp.jpg">
    <style>
        :root {
            --bg: linear-gradient(-45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            --text: #333;
            --glass: rgba(255, 255, 255, 0.3);
        }
        [data-theme="dark"] {
            --bg: linear-gradient(-45deg, #1a1a2e, #16213e, #0f3460);
            --text: #eee;
            --glass: rgba(0, 0, 0, 0.5);
        }
        * { margin: 0; padding: 0; box-sizing: border-box; transition: 0.4s; }
        body {
            min-height: 100vh;
            background: var(--bg);
            background-size: 400% 400%;
            animation: gradient 15s infinite;
            font-family: 'Segoe UI', sans-serif;
            color: var(--text);
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 20px;
        }
        @keyframes gradient { 0% {background-position: 0% 50%;} 50% {background-position: 100% 50%;} 100% {background-position: 0% 50%;} }
        
        .theme-btn { position: fixed; top: 20px; right: 20px; cursor: pointer; background: var(--glass); padding: 12px; border-radius: 50%; font-size: 1.5rem; border: 1px solid rgba(255,255,255,0.2); }
        
        .section-card {
            background: var(--glass);
            backdrop-filter: blur(10px);
            padding: 25px;
            border-radius: 20px;
            text-align: center;
            width: 100%;
            max-width: 350px;
            margin-bottom: 40px;
            border: 1px solid rgba(255,255,255,0.2);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        img { width: 100%; border-radius: 15px; border: 5px solid white; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        button {
            background: white; color: #ff758c; border: none;
            padding: 12px 25px; border-radius: 50px; font-weight: bold;
            cursor: pointer; margin-top: 15px; width: 100%;
        }
        hr { width: 50%; border: 0; border-top: 2px dashed rgba(255,255,255,0.5); margin: 10px auto; }
    </style>
</head>
<body>

    <div class="theme-btn" onclick="toggleTheme()" id="themeIcon">🌙</div>

    <h1>My Friends</h1>
    <p style="margin-bottom: 30px; opacity: 0.8;">নিচে সব কালেকশন আছে</p>

    <div class="section-card">
        <h3>Memory 01</h3>
        <hr>
        <img src="hk.png" alt="Old Image">
        <audio id="audio1" loop><source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg"></audio>
        <button onclick="playMusic('audio1', this)">▶ Play Music 1</button>
    </div>

    <div class="section-card">
        <h3>Memory 02</h3>
        <hr>
        <img src="nk.jpg?v=2" alt="New Image">
        <audio id="audio2" loop><source src="cid.mp3?v=2" type="audio/mpeg"></audio>
        <button onclick="playMusic('audio2', this)">▶ Play Music 2</button>
    </div>

    <script>
        function toggleTheme() {
            const body = document.body;
            const icon = document.getElementById("themeIcon");
            if (body.getAttribute("data-theme") === "dark") {
                body.removeAttribute("data-theme");
                icon.innerText = "🌙";
            } else {
                body.setAttribute("data-theme", "dark");
                icon.innerText = "☀️";
            }
        }

        function playMusic(id, btn) {
            const audio = document.getElementById(id);
            // অন্য সব অডিও বন্ধ করার জন্য (অপশনাল)
            document.querySelectorAll('audio').forEach(el => {
                if(el.id !== id) {
                    el.pause();
                    el.nextElementSibling.innerText = "▶ Play Music";
                }
            });

            if (audio.paused) {
                audio.play();
                btn.innerText = "⏸ Pause Music";
            } else {
                audio.pause();
                btn.innerText = "▶ Play Music";
            }
        }
    </script>
</body>
</html>
