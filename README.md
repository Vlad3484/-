<!DOCTYPE html>
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
      margin-bottom: 15px;
      width: 85%;
      max-width: 320px;
    }

    h1 {
      font-size: 12vw;
      margin-bottom: 5px;
    }

    p {
      font-size: 6vw;
      margin-top: 0;
    }

    .photos {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      margin-bottom: 10px;
      width: 100%;
    }

    .photos img {
      width: 85%;
      max-width: 180px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    }

    .audio {
      margin-bottom: 15px;
      width: 100%;
      display: flex;
      justify-content: center;
    }

    .audio button {
      padding: 8px 15px;
      font-size: 1rem;
      background-color: #ff5e5e;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      width: 80%;
      max-width: 240px;
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
      width: 12px;
      height: 12px;
      background: red;
      transform: rotate(45deg);
      animation: float 6s linear infinite;
    }

    .heart::before, .heart::after {
      content: '';
      position: absolute;
      width: 12px;
      height: 12px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -6px;
      left: 0;
    }

    .heart::after {
      left: -6px;
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

    /* Додаткові медіа-запити для ще кращої адаптації */
    @media (max-width: 480px) {
      .container {
        padding: 5px;
      }

      h1 {
        font-size: 16vw; /* Шрифт ще зменшений для маленьких екранів */
      }

      p {
        font-size: 7vw;
      }

      .photos img {
        width: 80%;
        max-width: 160px;
      }

      .audio button {
        font-size: 1.2rem; /* Трохи більший шрифт на мобільних */
        padding: 10px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Кохаю тебе, моє сонечко 🌞</h1>
    <p>Ти — найкраще, що зі мною траплялося 💛</p>
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
