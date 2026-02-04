<!DOCTYPE html>
<html>
<head>
    <title>For Devuzzee ❤️</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            margin: 0;
            padding: 20px;
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #ff758c, #ff7eb3);
            color: white;
            text-align: center;
            overflow: hidden;
            position: relative;
        }

        h1 {
            font-size: 34px;
            margin-bottom: 20px;
        }

        p {
            font-size: 22px;
            font-weight: bold;
            max-width: 600px;
            margin: 20px auto;
        }

        button {
            padding: 15px 25px;
            font-size: 18px;
            margin: 10px;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            position: relative;
            z-index: 10;
        }

        #yes { 
            background-color: #ff69b4;
        }

        #no { 
            background-color: #ff4d4d; 
            position: absolute; 
            top: 150px; 
            left: 50%; 
            transform: translateX(-50%);
        }

        .heart {
            position: fixed;
            color: pink;
            font-size: 20px;
            animation: float 4s linear infinite;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes float {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-800px); opacity: 0; }
        }

        .love-pop {
            position: fixed;
            color: red;
            font-size: 25px;
            animation: pop 1s ease forwards;
            pointer-events: none;
            z-index: 10;
        }

        @keyframes pop {
            0% { transform: scale(1); opacity: 1; }
            100% { transform: scale(2); opacity: 0; }
        }

        .star {
            position: fixed;
            width: 3px;
            height: 3px;
            background: white;
            border-radius: 50%;
            opacity: 0.8;
            pointer-events: none;
            animation: twinkle 2s infinite alternate;
            z-index: 0;
        }

        @keyframes twinkle {
            0% { opacity: 0.2; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.5); }
            100% { opacity: 0.2; transform: scale(1); }
        }

        #letter { display: none; text-align: center; }
    </style>
</head>
<body>

<h1>Itz for u Devuzzee my spcl one 😭🎀</h1>

<button id="yes">Open 💖</button>
<button id="no">Ignore 😏</button>

<div id="letter">
    <p id="loveLetter"></p>
</div>

<script>
    const yesBtn = document.getElementById('yes');
    const noBtn = document.getElementById('no');
    const letter = document.getElementById('letter');
    const loveLetter = document.getElementById('loveLetter');

    // Your special line
    const letterText = `Ur not just my best friend — ur the one that the soul who understands my silence 😭💫`;

    function typeText(element, text, speed = 50) {
        let i = 0;
        element.innerHTML = '';
        const interval = setInterval(() => {
            element.innerHTML += text[i];
            i++;
            if (i >= text.length) clearInterval(interval);
        }, speed);
    }

    yesBtn.addEventListener('click', showLetter);
    yesBtn.addEventListener('touchstart', showLetter);

    function showLetter(e){
        e.preventDefault();
        letter.style.display = 'block';
        yesBtn.style.display = 'none';
        noBtn.style.display = 'none';
        typeText(loveLetter, letterText, 50);
    }

    noBtn.addEventListener('click', moveNo);
    noBtn.addEventListener('touchstart', moveNo);

    function moveNo(e){
        e.preventDefault();
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        noBtn.style.left = x + 'px';
        noBtn.style.top = y + 'px';

        const love = document.createElement('div');
        love.className = 'love-pop';
        love.innerHTML = 'I ❤️ YOU';
        love.style.left = x + 'px';
        love.style.top = y + 'px';
        document.body.appendChild(love);

        setTimeout(()=>love.remove(), 1000);
    }

    setInterval(()=>{
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.innerHTML = '💖';
        heart.style.left = Math.random() * window.innerWidth + 'px';
        heart.style.bottom = '0px';
        document.body.appendChild(heart);
        setTimeout(()=>heart.remove(), 4000);
    }, 500);

    setInterval(()=>{
        const star = document.createElement('div');
        star.className = 'star';
        star.style.left = Math.random() * window.innerWidth + 'px';
        star.style.top = Math.random() * window.innerHeight + 'px';
        star.style.width = Math.random()*3 + 2 + 'px';
        star.style.height = Math.random()*3 + 2 + 'px';
        document.body.appendChild(star);
        setTimeout(()=>star.remove(), 2000 + Math.random()*2000);
    }, 300);
</script>

</body>
</html>
