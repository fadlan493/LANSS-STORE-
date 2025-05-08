<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Kotak Cinta Romantis</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #ffe6f0, #fff0f5);
      margin: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      position: relative;
    }

    #dari {
      position: absolute;
      top: 15px;
      right: 20px;
      font-size: 26px;
      color: #ff1493;
      font-weight: bold;
      text-shadow: 1px 1px 2px white;
    }

    #heart {
      font-size: 90px;
      color: hotpink;
      animation: float 2s infinite;
    }

    #box {
      width: 420px;
      height: 250px;
      background-color: red;
      color: white;
      font-size: 30px;
      font-weight: bold;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      border-radius: 20px;
      cursor: pointer;
      transition: all 0.5s ease;
      box-shadow: 0 0 35px rgba(255, 0, 0, 0.8);
      margin-top: 20px;
      text-shadow: 1px 1px 3px #000;
    }

    .hearts {
      margin-top: 30px;
      font-size: 40px;
      color: pink;
      animation: float 1.5s infinite;
    }

    .rain-heart {
      position: absolute;
      top: -50px;
      font-size: 24px;
      color: pink;
      animation: fall 5s linear forwards;
      pointer-events: none;
    }

    @keyframes float {
      0% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0); }
    }

    @keyframes fall {
      0% { transform: translateY(0); opacity: 1; }
      100% { transform: translateY(100vh); opacity: 0; }
    }

    .glow {
      color: #fff;
      text-shadow: 0 0 10px #ff69b4, 0 0 20px #ff69b4;
    }
  </style>
</head>
<body>

<div id="dari">DARI FADLAN</div>
<div id="heart">❤️</div>
<div id="box">Coba pencet!</div>
<div id="hearts" class="hearts" style="display: none;">♥ ♥ ♥</div>

<script>
  let count = 0;
  const box = document.getElementById('box');
  const hearts = document.getElementById('hearts');
  const heart = document.getElementById('heart');

  box.addEventListener('click', () => {
    count++;

    if (count === 1) {
      box.textContent = 'Pencet lagi ya!';
    } else if (count === 2) {
      box.textContent = 'Terus pencet lagi~';
    } else if (count === 3) {
      box.textContent = 'Kotak pencet 1 kali lagi~';
    } else if (count === 4) {
      box.textContent = 'I LOVE YOU ELSA';
      box.classList.add('glow');
      box.style.backgroundColor = '#ff69b4';
      box.style.fontSize = '36px';
      hearts.style.display = 'block';
      heart.style.display = 'none';
      startHeartRain();
    }
  });

  function startHeartRain() {
    for (let i = 0; i < 5; i++) {
      const heart = document.createElement('div');
      heart.classList.add('rain-heart');
      heart.innerHTML = '♥';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (3 + Math.random() * 2) + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }

    setInterval(() => {
      for (let i = 0; i < 5; i++) {
        const heart = document.createElement('div');
        heart.classList.add('rain-heart');
        heart.innerHTML = '♥';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (3 + Math.random() * 2) + 's';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 6000);
      }
    }, 5000);
  }
</script>

</body>
</html>
