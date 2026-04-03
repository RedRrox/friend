<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    
    <link rel="icon" type="image/jpeg" href="rrp.jpg?v=2.0">

    <style>
        :root {
            --bg: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            --container-bg: rgba(255, 255, 255, 0.15);
            --text-color: white;
            --accent-color: #ffffff;
        }

        [data-theme="dark"] {
            --bg: linear-gradient(-45deg, #121212, #1f1f1f, #2c3e50, #000000);
            --container-bg: rgba(0, 0, 0, 0.6);
            --text-color: #ff758c;
            --accent-color: #00d2ff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: all 0.5s ease;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: var(--bg);
            background-size: 400% 400%;
            animation: gradientMove 10s ease infinite;
            color: var(--text-color);
            overflow-x: hidden;
        }

        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .main-card {
            background: var(--container-bg);
            backdrop-filter: blur(15px);
            padding: 30px;
            border-radius: 25px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
        }

        .profile-frame {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 0 auto 20px;
        }

        .profile-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 20px;
            border: 5px solid white;
            animation: bounce 3s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        h1 {
            font-size: 2rem;
            margin-bottom: 15px;
            letter-spacing: 2px;
        }

        p {
            font-size: 14px;
            line-height: 1.6;
            margin-bottom: 25px;
            color: rgba(255, 255, 255, 0.9);
        }

        [data-theme="dark"] p {
            color: #ddd;
        }

        .btn-group {
            display: flex;
            flex-direction: column;
            gap: 15px;
            align-items: center;
        }

        .music-btn {
            background: white;
            color: #ff3e6c;
            border: none;
            padding: 12px 30px;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .theme-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            background: var(--container-bg);
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
        <div class="profile-frame">
            <img src="hk.png" alt="Profile">
        </div>

        <h1>FRIENDS</h1>

        <p>ধন্যবাদ আমাদের ওয়েবসাইটে আসার জন্য! আমাদের ওয়েবসাইটটি কারো অপমান বা ছোট করার জন্য তৈরি করা হয়নি। এটি বিনোদনের উদ্দেশ্যে তৈরি।</p>

        <div class="btn-group">
            <audio id="mySong" loop>
                <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
            </audio>
            
            <button class="music-btn" onclick="playMusic()">
                <span id="icon">▶</span> <span id="text">Play Music</span>
            </button>
        </div>
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
