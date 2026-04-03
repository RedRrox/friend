<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    
    <link rel="icon" type="image/jpeg" href="./rrp.jpg">

    <style>
        :root {
            --bg: linear-gradient(-45deg, #1a2a6c, #b21f1f, #fdbb2d);
            --text: #ffffff;
            --glass: rgba(255, 255, 255, 0.1);
        }

        [data-theme="dark"] {
            --bg: linear-gradient(-45deg, #000000, #434343);
            --text: #00d2ff;
            --glass: rgba(0, 0, 0, 0.7);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; transition: 0.5s; }

        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background: var(--bg);
            background-size: 400% 400%;
            animation: move 12s infinite;
            font-family: 'Segoe UI', sans-serif;
            color: var(--text);
            padding: 20px;
            text-align: center;
        }

        @keyframes move {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .theme-btn {
            position: fixed;
            top: 20px;
            right: 20px;
            background: var(--glass);
            border: 1px solid rgba(255,255,255,0.2);
            padding: 12px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 20px;
        }

        .card {
            background: var(--glass);
            backdrop-filter: blur(15px);
            padding: 30px;
            border-radius: 25px;
            border: 1px solid rgba(255,255,255,0.1);
            max-width: 350px;
            width: 100%;
        }

        img.main-img {
            width: 100%;
            border-radius: 15px;
            border: 4px solid white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
            margin-bottom: 20px;
        }

        .music-btn {
            margin-top: 20px;
            background: #fff;
            color: #333;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }
    </style>
</head>
<body>

    <div class="theme-btn" onclick="toggle()">🌙</div>

    <div class="card">
        <img src="./nk.jpg" alt="Photo" class="main-img">
        
        <h1>Friends</h1>
        <p style="margin: 15px 0; font-size: 14px; opacity: 0.8;">
            ধন্যবাদ আসার জন্য! এটি বিনোদনের উদ্দেশ্যে তৈরি।
        </p>

        <audio id="audio" loop>
            <source src="./cid.mp3" type="audio/mpeg">
        </audio>

        <button class="music-btn" onclick="play()">
            <span id="i">▶</span> <span id="t">Play Music</span>
        </button>
    </div>

    <script>
        function toggle() {
            document.body.hasAttribute("data-theme") ? 
            document.body.removeAttribute("data-theme") : 
            document.body.setAttribute("data-theme", "dark");
        }

        function play() {
            var a = document.getElementById("audio");
            var i = document.getElementById("i");
            var t = document.getElementById("t");
            if(a.paused) { a.play(); i.innerText="⏸"; t.innerText="Pause"; }
            else { a.pause(); i.innerText="▶"; t.innerText="Play Music"; }
        }
    </script>
</body>
</html>
