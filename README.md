<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>friendscot Official Site</title>
    <style>
        /* পুরো পেজের ডিজাইন */
        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: white;
            /* ব্যাকগ্রাউন্ড কালার চেঞ্জিং অ্যানিমেশন */
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradientBG 12s ease infinite;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* নতুন নাম: friendscot */
        h1 {
            font-size: 2.8rem;
            margin-bottom: 25px;
            text-shadow: 3px 5px 15px rgba(0,0,0,0.4);
            letter-spacing: 2px;
        }

        /* ইমেজের ডিজাইন ও অ্যানিমেশন */
        .image-container {
            width: 280px;
            max-width: 85%;
        }

        img {
            width: 100%;
            height: auto;
            border-radius: 25px; /* হালকা রাউন্ডেড শেপ */
            border: 6px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 15px 45px rgba(0,0,0,0.6);
            animation: floatImage 4s ease-in-out infinite;
        }

        @keyframes floatImage {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-25px); }
        }

        /* অডিও প্লেয়ার */
        audio {
            margin-top: 40px;
            filter: drop-shadow(0 8px 20px rgba(0,0,0,0.4));
            opacity: 0.9;
        }

        /* নিচের টেক্সট */
        .welcome-text {
            margin-top: 25px;
            font-size: 1.1rem;
            font-weight: 300;
            background: rgba(0, 0, 0, 0.2);
            padding: 8px 20px;
            border-radius: 50px;
        }
    </style>
</head>
<body>

    <h1>friendscot.github.io</h1>

    <div class="image-container">
        <img src="hk.png" alt="friendscot Profile">
    </div>

    <audio controls>
        <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
        আপনার ব্রাউজারটি অডিও সাপোর্ট করে না।
    </audio>

    <div class="welcome-text">Welcome to friendscot animated world!</div>

</body>
</html>
