# YouAreMyValentine-
<html lang="th">
<head>
    <link href="https://fonts.googleapis.com/css2?family=Sriracha&display=swap" rel="stylesheet">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 Surprise for You 💖</title>
    <style>
        body {
            text-align: center;
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to bottom, #0b1445, #1a237e, #3f51b5); /* พื้นหลังท้องฟ้ากลางคืน */
            color: #ff4081;
            margin: 0;
            padding: 20px;
            overflow: hidden;
            position: relative;
        }
        h1 {
            font-size: 28px;
            margin-top: 50px;
            color: white;
        }
        .hidden {
            display: none;
        }
        button {
            background-color: transparent;
            color: white;
            border: none;
            padding: 15px 20px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 8px;
            margin-top: 20px;
        }
        button:hover {
            backgroung-color: #e91e63
            
        }

        /* แผ่นเสียงหมุน */
        .record-container {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 20px auto;
        }
        .record {
            width: 100%;
            height: 100%;
            background: url('https://s.isanook.com/ca/0/ud/280/1401475/105584766_3260307764032815_54.jpg?ip/crop/w1200h700/q80/webp') no-repeat center;
            background-size: cover;
            border-radius: 50%;
            animation: spin 6s linear infinite;
        }
        .record img {
            position: absolute;
            width: 80px;
            height: 80px;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: black;
        }
        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        .song-title {
            font-size: 18px;
            font-weight: bold;
            margin-top: 10px;
            color: white;
        }

        /* ข้อความเซอร์ไพรส์ */
        #message {
            font-size: 22px;
            font-weight: bold;
            color: white;
            margin-top: 20px;
            display: none;
            
        }

        /* เอฟเฟกต์หัวใจลอย */
        .heart {
            position: absolute;
            color: red;
            font-size: 24px;
            animation: floatUp 4s linear infinite;
        }
        
        /* เอฟเฟกต์หัวใจลอย */
        .star {
            position: absolute;
            color: yellow;
            font-size: 24px;
            animation: floatUp 4s linear infinite;
        }
        @keyframes floatUp {
            0% {
                transform: translateY(0);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }

        /* เอฟเฟกต์ดาวตก */
        .shooting-star {
            position: absolute;
            width: 5px;
            height: 5px;
            background-color: pink;
            box-shadow: 0 0 8px pink;
            border-radius: 50%;
            animation: shootingStar 2s linear infinite;
        }
        @keyframes shootingStar {
            0% {
                transform: translate(100vw, -10vh);
                opacity: 1;
            }
            100% {
                transform: translate(-10vw, 100vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <h1>𓄹 ❀˖*💘𝓗𝓪𝓹𝓹𝔂 𝓥𝓪𝓵𝓮𝓷𝓽𝓲𝓷𝓮 𝓓𝓪𝔂💘˚⋆ ࿐・ </h1>
    <button onclick="showSurprise()"> ⭐ </button>

    <div id="message" class="hidden"> เค้ารักคุณนะต้าว เป็นอีกวันพิเศษที่เราได้มีกันและกัน ขอบคุณคุณสำหรับทุกๆ เรื่องเลยนะ อยู่เปงไอ้ตูดของเค้าแบบนี้ไปนานๆนะ เค้ารักคุณ! </div>
    <script>
        function showSurprise() {
            document.getElementById('message').style.display = "block";
            startFloatingHearts(); // เริ่มเอฟเฟกต์หัวใจ
        }

        function startFloatingHearts() {
            setInterval(() => {
                let heart = document.createElement("div");
                heart.classList.add("heart");
                heart.innerHTML = "💖"; // อีโมจิหัวใจ
                heart.style.left = Math.random() * 100 + "vw"; // สุ่มตำแหน่งแนวนอน
                heart.style.top = "100vh"; // เริ่มจากด้านล่าง
                heart.style.fontSize = Math.random() * 20 + 20 + "px"; // สุ่มขนาดหัวใจ
                document.body.appendChild(heart);

                // ลบหัวใจเมื่อออกจากจอ
                setTimeout(() => heart.remove(), 3000);
            }, 500); // สร้างหัวใจทุก 0.5 วินาที
        }
    </script>

    <div class="record-container">
        <div class="record">
            <img src="https://yt3.googleusercontent.com/ytc/AIdro_mOnqMkA1pfhFtKyvH7aMlFsx5OaOeQH5RbGykb7w=s900-c-k-c0x00ffffff-no-rj" alt="Album Cover">
        </div>
    </div>
    <p class="song-title">💖 เพลง: ดาวหางฮัลเลย์ - fellow fellow 💖</p>

    <div id="player"></div>

    <script>
        // โหลด YouTube API
        var tag = document.createElement('script');
        tag.src = "https://www.youtube.com/iframe_api";
        var firstScriptTag = document.getElementsByTagName('script')[0];
        firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

        var player;
        function onYouTubeIframeAPIReady() {
            player = new YT.Player('player', {
                height: '0',
                width: '0',
                videoId: 'jx28LXc3Yvw', // ใส่ ID วิดีโอ YouTube
                playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'jx28LXc3Yvw' }
            });
        }

        function showSurprise() {
            document.getElementById('message').style.display = "block";
            playMusic();
            createFloatingHearts();
            createShootingStars();
        }

        function playMusic() {
            if (player) {
                player.playVideo();
            }
        }

        // หัวใจลอยขึ้น
        function createFloatingHearts() {
            for (let i = 0; i < 10; i++) {
                let heart = document.createElement("div");
                heart.innerHTML = "❤️";
                heart.classList.add("heart");
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.top = "100vh";
                heart.style.position = "absolute";
                heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 4000);
            }
        }

        // หัวใจลอยขึ้น
        function createFloatingStars() {
            for (let i = 0; i < 10; i++) {
                let star = document.createElement("div");
                heart.innerHTML = "⭐";
                heart.classList.add("star");
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.top = "100vh";
                heart.style.position = "absolute";
                heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
                document.body.appendChild(star);
                setTimeout(() => star.remove(), 4000);
            }
        }

        // ดาวตก
        function createShootingStars() {
            for (let i = 0; i < 5; i++) {
                let star = document.createElement("div");
                star.classList.add("shooting-star");
                star.style.left = Math.random() * 100 + "vw";
                star.style.top = Math.random() * 50 + "vh";
                document.body.appendChild(star);
                setTimeout(() => star.remove(), 2000);
            }
        }
    </script>

</body>
</html>
