<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Genshin Impact Character Roulette</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #222;
            color: white;
        }
        .roulette-container {
            position: relative;
            width: 300px;
            height: 300px;
            margin: 50px auto;
            border-radius: 50%;
            border: 5px solid #fff;
            overflow: hidden;
        }
        .wheel {
            width: 100%;
            height: 100%;
            position: absolute;
            background: conic-gradient(red, yellow, blue, green, purple, orange);
            border-radius: 50%;
            transition: transform 3s ease-out;
        }
        .pointer {
            width: 20px;
            height: 40px;
            background: white;
            position: absolute;
            top: -10px;
            left: 50%;
            transform: translateX(-50%);
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            margin-top: 20px;
            cursor: pointer;
        }
        .result {
            font-size: 24px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Genshin Impact Character Roulette</h1>
    <div class="roulette-container">
        <div class="pointer"></div>
        <div class="wheel" id="wheel"></div>
    </div>
    <button onclick="spinRoulette()">Spin!</button>
    <div class="result" id="result"></div>

    <script>
        const characters = ["Aether", "Lumine", "Albedo", "Amber", "Arataki Itto", "Barbara", "Beidou", "Bennett", "Chongyun", "Diluc", "Diona", "Eula", "Fischl", "Ganyu", "Gorou", "Hu Tao", "Jean", "Kaeya", "Kazuha", "Keqing", "Klee", "Kokomi", "Lisa", "Mona", "Ningguang", "Noelle", "Qiqi", "Raiden Shogun", "Razor", "Rosaria", "Sayu", "Shenhe", "Sucrose", "Tartaglia", "Thoma", "Venti", "Xiangling", "Xiao", "Xingqiu", "Xinyan", "Yanfei", "Yoimiya", "Yun Jin", "Zhongli"];
        
        function spinRoulette() {
            const wheel = document.getElementById("wheel");
            const result = document.getElementById("result");
            const randomIndex = Math.floor(Math.random() * characters.length);
            const degrees = 3600 + (randomIndex * (360 / characters.length));
            
            wheel.style.transform = `rotate(${degrees}deg)`;
            setTimeout(() => {
                result.innerText = `🎉 You got: ${characters[randomIndex]}! 🎉`;
            }, 3000);
        }
    </script>
</body>
</html>
