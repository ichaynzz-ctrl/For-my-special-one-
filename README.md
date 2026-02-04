<!DOCTYPE html>
<html>
<head>
    <title>Devuzze ❤️ Valentine Surprise</title>
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
        }

        h1 {
            font-size: 36px;
            margin-bottom: 20px;
        }

        p {
            font-size: 18px;
            line-height: 1.8;
            max-width: 600px;
            margin: 20px auto;
        }

        .signature {
            margin-top: 20px;
            font-style: italic;
        }

        button {
            padding: 15px 25px;
            font-size: 18px;
            margin: 10px;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            position: relative;
            z-index: 10; /* Above hearts */
        }

        #yes { background-color: #00ff88; }
        #no { background-color: #ff4d4d; position: absolute; top: 150px; left: 50%; transform: translateX(-50%); }

        /* Floating hearts */
        .heart {
            position: fixed;
            color: pink;
            font-size: 20px;
            animation: float 4s linear infinite;
            pointer-events: none; /* So buttons clickable */
            z-index: 1;
        }

        @keyframes float {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-800px); opacity: 0; }
        }

        /* I LOVE YOU pop */
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

        #letter { display: none; }
    </style>
</head>
<body>

<h1>Will you be my Valentine? 💘</h1>

<button id="yes">Yes 💖</button>
<button id="no">No 😏</button>

<div id="letter">
    <p>
    Devuzze… ❤️<br><br>
    If you’re reading this, it means you scanned something made only for you 🤭<br>
    I don’t know when it started…<br>
    Maybe from that first call,<br>
    maybe from your silly 😝 face,<br>
    or maybe from the way you say “dahhh” before cutting the call…<br><br>
    But somewhere between all those little moments,<br>
    you became special to me.<br>
    Not loudly.<br>
    Not suddenly.<br>
    Just peacefully… like stars appearing one by one 🌠<br><br>
    You irritate me, tease me, make me smile for no reason…<br>
    and I think that’s my favorite part.<br><br>
    I don’t know what the future holds.<br>
    But right now, I just want you to know —<br>
    You make my days softer.<br>
    You make my heart calmer.<br>
    And you mean more to me than I say out loud.<br><br>
    Happy Valentine’s Day, Devu ❤️
    </p>

    <div class="signature">– From someone who smiles because of you 🙈</div>
</div>

<script>
    const yesBtn = document.getElementById('yes');
    const noBtn = document.getElementById('no');
    const letter = document.getElementById('letter');

    // Mobile-friendly Yes button
    yesBtn.addEventListener('click', showLetter);
    yesBtn.addEventListener('touchstart', showLetter);

    function showLetter(e){
        e.preventDefault();
        letter.style.display = 'block';
        yesBtn.style.display = 'none';
        noBtn.style.display = 'none';
    }

    // Mobile-friendly No button
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

    // Floating hearts continuously
    setInterval(()=>{
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.innerHTML = '💖';
        heart.style.left = Math.random() * window.innerWidth + 'px';
        heart.style.bottom = '0px';
        document.body.appendChild(heart);
        setTimeout(()=>heart.remove(), 4000);
    }, 500);
</script>

</body>
</html>
