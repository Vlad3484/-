<html lang="uk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Кохаю тебе, моє сонечко</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(120deg, #ffecd2, #fcb69f);
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      overflow: hidden;
    }

    .container {
      text-align: center;
      color: #fff;
      padding: 10px;
      background: rgba(255, 255, 255, 0.3);
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.2);
      margin-bottom: 10px;
      width: 80%;
      max-width: 320px;
    }

    h1, p {
      font-size: 3vw; /* Однаковий розмір для заголовка і тексту */
      margin-bottom: 3px;
      margin-top: 0;
    }

    .poem {
      font-size: 3vw; /* Трохи менший розмір для вірша */
      font-style: italic;
      color: #fff;
      margin-top: 20px;
    }

    .photos {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 6px;
      margin-bottom: 10px;
      width: 100%;
    }

    .photos img {
      width: 34%;
      max-width: 56px;
      border-radius: 5px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.3);
    }

    .audio {
      margin-bottom: 10px;
      width: 100%;
      display: flex;
      justify-content: center;
    }

    .audio button {
      padding: 4px 6px;
      font-size: 0.8rem;
      background-color: #ff5e5e;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      width: 80%;
      max-width: 160px;
    }

    .audio button:hover {
      background-color: #ff3b3b;
    }

    .hearts {
      position: fixed;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      pointer-events: none;
      z-index: 0;
    }

    .heart {
      position: absolute;
      width: 4px;
      height: 4px;
      background: red;
      transform: rotate(45deg);
      animation: float 6s linear infinite;
    }

    .heart::before, .heart::after {
      content: '';
      position: absolute;
      width: 4px;
      height: 4px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -2px;
      left: 0;
    }

    .heart::after {
      left: -2px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }

    @media (max-width: 480px) {
      .container {
        padding: 6px;
      }

      h1, p {
        font-size: 4vw;
      }

      .poem {
        font-size: 5vw; /* Для мобільних пристроїв зручніше */
      }

      .photos img {
        width: 20%;
        max-width: 40px;
      }

      .audio button {
        font-size: 1.2rem;
        padding: 6px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Кохаю тебе, моє сонечко 🌞</h1>
    <p>Ти — найкраще, що зі мною траплялося 💛</p>
    <div class="poem">
      <p>Жадан, "Про кохання"</p>
      <p>Я тебе люблю. І ти мене любиш.<br>
      Не зважай на те, що нас розлучають долі,<br>
      Ми будемо разом, хоч би що сталося.<br>
      Ти — моє світло, моє сонце.<br>
      Я тебе люблю.</p>
    </div>
  </div>

  <div class="photos">
    <img src="https://i.postimg.cc/HsNYrsQ0/photo2-jpg.jpg" alt="Наша пара">
    <img src="https://i.postimg.cc/52Z2RNy9/photo1-jpg.jpg" alt="Photo 2">
    <img src="https://i.postimg.cc/L6qtYDqJ/photo3-jpg.jpg" alt="Photo 3">
  </div>

  <div class="audio">
    <button onclick="playAudio()">Відтворити пісню</button>
    <audio id="audio" loop>
      <source src="https://muzka.cc/uploads/files/2023-03/1679586978_tik-bez-tebe.mp3" type="audio/mpeg">
      Ваш браузер не підтримує аудіо.
    </audio>
  </div>

  <div class="hearts" id="hearts"></div>

  <script>
    const heartsContainer = document.getElementById('hearts');
    const audio = document.getElementById('audio');

    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (5 + Math.random() * 5) + 's';
      heartsContainer.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 10000);
    }

    setInterval(createHeart, 300);

    function playAudio() {
      audio.play();
    }
  </script>
</body>
</html>
