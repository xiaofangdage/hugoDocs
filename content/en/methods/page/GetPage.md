<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>六年之约，唐婷，我喜欢你</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(45deg, #ff9a9e 0%, #fad0c4 99%, #fad0c4 100%);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            position: relative;
        }

        .container {
            text-align: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
            z-index: 1;
        }

        h1 {
            color: #e91e63;
            font-size: 3em;
            margin-bottom: 20px;
        }

        p {
            font-size: 1.2em;
            line-height: 1.6;
            color: #333;
            margin-bottom: 30px;
        }

        button {
            padding: 15px 30px;
            font-size: 1.2em;
            background: #e91e63;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s ease;
            margin: 10px;
        }

        button:hover {
            background: #c2185b;
        }

        .hidden {
            display: none;
        }

        .heart {
            position: fixed;
            width: 20px;
            height: 20px;
            background: red;
            transform: rotate(-45deg);
            animation: fall 5s linear infinite;
        }

        .heart::before,
        .heart::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: red;
            border-radius: 50%;
        }

        .heart::before {
            top: -10px;
            left: 0;
        }

        .heart::after {
            left: 10px;
            top: 0;
        }

        @keyframes fall {
            0% {
                top: -20px;
            }

            100% {
                top: 100vh;
            }
        }

        #finalMessage {
            background: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 2;
        }
    </style>
</head>

<body>
    <div class="container" id="startPage">
        <h1>唐婷，这六年的故事我想续写</h1>
        <p>亲爱的唐婷，我们一起走过了整整六年。这六年里，我们分享了无数的喜怒哀乐，每一个瞬间都在我心中熠熠生辉。随着时间的推移，我发现对你的感情早已超越了朋友的界限。你就像我生活中的阳光，照亮了每一个角落。我喜欢你，从心动到如今的满心欢喜。</p>
        <button id="startButton">开启专属惊喜</button>
    </div>
    <div class="container hidden" id="questionPage">
        <h1>唐婷，我喜欢你</h1>
        <p>在这六年的时光里，我慢慢发现你已经成为了我生命中最重要的人。我想一直陪伴在你身边，照顾你，爱护你。你愿意做我的女朋友吗？</p>
        <button id="yesButton">同意做我女朋友</button>
        <button id="noButton">再考虑考虑</button>
    </div>
    <div id="finalMessage" class="hidden">
        <h1>太开心啦！</h1>
        <p>唐婷，谢谢你的同意，我会用我的一生去爱你、呵护你，让你成为世界上最幸福的女孩！</p>
        <img src="/img/6fe426ab25bde49cb42acf4075ff038.jpg" alt="" />
    </div>

    <script>
        const startButton = document.getElementById('startButton');
        const startPage = document.getElementById('startPage');
        const questionPage = document.getElementById('questionPage');
        const yesButton = document.getElementById('yesButton');
        const noButton = document.getElementById('noButton');
        const finalMessage = document.getElementById('finalMessage');

        startButton.addEventListener('click', function () {
            startPage.classList.add('hidden');
            questionPage.classList.remove('hidden');
        });

        yesButton.addEventListener('click', function () {
            questionPage.classList.add('hidden');
            finalMessage.classList.remove('hidden');
            createHearts(50);
        });

        noButton.addEventListener('click', function () {
            alert('再好好考虑一下嘛，我真的很喜欢你！');
        });

        function createHearts(count) {
            for (let i = 0; i < count; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDuration = Math.random() * 5 + 3 + 's';
                document.body.appendChild(heart);
            }
        }
    </script>
</body>

</html>
