<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    <style>
        :root {
            --bg: linear-gradient(-45deg, #23a6d5, #23d5ab, #ee7752, #e73c7e);
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            display: flex; justify-content: center; align-items: center;
            min-height: 100vh; background: var(--bg);
            background-size: 400% 400%; animation: gradient 10s infinite;
            font-family: sans-serif; color: white; padding: 20px;
        }
        @keyframes gradient { 0% {background-position: 0% 50%;} 50% {background-position: 100% 50%;} 100% {background-position: 0% 50%;} }
        .card {
            background: rgba(255, 255, 255, 0.2); backdrop-filter: blur(10px);
            padding: 30px; border-radius: 20px; text-align: center;
            border: 1px solid rgba(255,255,255,0.3); width: 100%; max-width: 350px;
        }
        img {
            width: 100%; border-radius: 15px; border: 5px solid white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2); margin-bottom: 20px;
        }
        button {
            background: white; color: #e73c7e; border: none;
            padding: 12px 30px; border-radius: 50px; font-weight: bold;
            cursor: pointer; margin-top: 15px;
        }
    </style>
</head>
<body>
    <div class="card">
        <img src="https://raw.githubusercontent.com/RedRrox/friend/main/nk.jpg" alt="Friend Photo">
        <h1>Friends</h1>
        <p style="margin-top:10px; font-size: 14px; opacity: 0.9;">এটি বিনোদনের উদ্দেশ্যে তৈরি।</p>
        
        <audio id="m" loop>
            <source src="https://raw.githubusercontent.com/RedRrox/friend/main/cid.mp3" type="audio/mpeg">
        </audio>
        <button onclick="p()">▶ Play Music</button>
    </div>
    <script>
        function p(){
            var a = document.getElementById("m");
            if(a.paused) { a.play(); document.querySelector('button').innerText = "⏸ Pause Music"; }
            else { a.pause(); document.querySelector('button').innerText = "▶ Play Music"; }
        }
    </script>
</body>
</html>
