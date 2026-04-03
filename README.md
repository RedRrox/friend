<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    <link rel="icon" type="image/jpeg" href="rrp.jpg">
    <style>
        :root {
            --bg: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            --glass: rgba(255, 255, 255, 0.2);
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background: var(--bg);
            background-size: 400% 400%;
            animation: gradient 10s infinite;
            font-family: sans-serif;
            color: white;
            padding: 20px;
        }
        @keyframes gradient { 0% {background-position: 0% 50%;} 50% {background-position: 100% 50%;} 100% {background-position: 0% 50%;} }
        .container {
            background: var(--glass);
            backdrop-filter: blur(10px);
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.3);
            max-width: 380px;
        }
        img {
            width: 100%;
            border-radius: 15px;
            border: 5px solid white;
            margin-bottom: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        button {
            background: white;
            color: #e73c7e;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <img src="nk.jpg?v=123" alt="Friend Photo">
        <h1>Friends</h1>
        <p style="margin-top:10px; font-size: 14px; opacity: 0.9;">এটি বিনোদনের উদ্দেশ্যে তৈরি।</p>
        
        <audio id="m" loop><source src="cid.mp3" type="audio/mpeg"></audio>
        <button onclick="p()">▶ Play Music</button>
    </div>
    <script>
        function p(){
            var a = document.getElementById("m");
            a.paused ? a.play() : a.pause();
        }
    </script>
</body>
</html>
