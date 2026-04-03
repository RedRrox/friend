<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    
    <link rel="icon" type="image/jpeg" href="rrp.jpg?v=2.1">

    <style>
        :root {
            --bg: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            --card-bg: rgba(255, 255, 255, 0.2);
            --text: white;
        }

        [data-theme="dark"] {
            --bg: linear-gradient(-45deg, #121212, #1f1f1f, #2c3e50, #000000);
            --card-bg: rgba(0, 0, 0, 0.6);
            --text: #ff758c;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; transition: 0.5s; }

        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: var(--bg);
            background-size: 400% 400%;
            animation: gradientMove 10s ease infinite;
            font-family: sans-serif;
            color: var(--text);
        }

        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .main-card {
            background: var(--card-bg);
            backdrop-filter: blur(15px);
            padding: 30px;
            border-radius: 25px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
            width: 350px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
        }

        .profile-img {
            width: 220px;
            height: 220px;
            object-fit: cover;
            border-radius: 15px;
            border: 5px solid white;
            margin-bottom: 20px;
            animation: bounce 3s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        h1 { margin-bottom: 10px; letter-spacing: 2px; }

        p { font-size: 14px; line-height: 1.5; margin-bottom: 20px; opacity: 0.9; }

        .music-btn {
            background: white;
            color: #ff3e6c;
            border: none;
            padding: 12px 25px;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            margin: 0 auto;
        }

        .theme-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            background: var(--card-bg);
            border: 1px solid rgba(255, 255, 255, 0.3);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
    </style>
</head>
<body>

    <button class="theme-toggle" onclick="toggleTheme()" id="tBtn">🌙</button>

    <div class="main-card">
        <img src="hk.png" class="profile-img" alt="Profile">
        <h1>FRIENDS</h1>
        <p>ধন্যবাদ আমাদের ওয়েবসাইটে আসার জন্য! এটি সম্পূর্ণভাবে মজা এবং বিনোদনের উদ্দেশ্যে তৈরি।</p>
        
        <audio id="mySong" loop>
            <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
        </audio>
        
        <button class="music-btn" onclick="playMusic()">
            <span id="icon">▶</span> <span id="text">Play Music</span>
        </button>
    </div>

    <script>
        function toggleTheme() {
            const body = document.body;
            const btn = document.getElementById("tBtn");
            if(body.hasAttribute("data-theme")) {
                body.removeAttribute("data-theme");
                btn.innerText = "🌙";
            } else {
                body.setAttribute("data-theme", "dark");
                btn.innerText = "☀️";
            }
        }

        function playMusic() {
            const audio = document.getElementById("mySong");
            const icon = document.getElementById("icon");
            const text = document.getElementById("text");
            if(audio.paused) {
                audio.play();
                icon.innerText = "⏸";
                text.innerText = "Pause Music";
            } else {
                audio.pause();
                icon.innerText = "▶";
                text.innerText = "Play Music";
            }
        }
    </script>
</body>
</html>
