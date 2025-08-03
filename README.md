# Friendship-day
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Friendship Day 💖</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      height: 100vh;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: linear-gradient(to right, #ffdee9, #ffc3a0);
      position: relative;
    }

    .envelope {
      width: 500px;
      height: 300px;
      background: #fff;
      border: 3px solid #ff4d6d;
      border-radius: 10px;
      position: relative;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
      cursor: pointer;
      z-index: 2;
      overflow: hidden;
    }

    .flap {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 50%;
      background-color: #ff4d6d;
      clip-path: polygon(0 0, 100% 0, 50% 100%);
      transform-origin: top;
      transition: transform 0.6s ease;
      z-index: 3;
    }

    .envelope.open .flap {
      transform: rotateX(-180deg);
    }

    .card {
      position: relative;
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.6s ease, transform 0.6s ease;
      z-index: 2;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      padding: 20px;
      box-sizing: border-box;
    }

    .envelope.open .card {
      opacity: 1;
      transform: translateY(0);
    }

    .card h2 {
      color: #ff4d6d;
      margin-bottom: 10px;
      font-size: 26px;
      text-align: center;
    }

    .scroll-area {
      flex: 1;
      overflow-y: auto;
      padding-right: 8px;
      text-align: justify;
    }

    .scroll-area::-webkit-scrollbar {
      width: 6px;
    }

    .scroll-area::-webkit-scrollbar-thumb {
      background: #ff4d6d;
      border-radius: 3px;
    }

    .scroll-area p {
      font-size: 16px;
      color: #444;
      line-height: 1.6;
      margin: 0;
    }

    .footer {
      margin-top: 30px;
      font-size: 15px;
      color: #800020;
      z-index: 2;
    }

    .heart {
      font-size: 22px;
      color: #ff4d6d;
      animation: beat 1s infinite;
    }

    @keyframes beat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.3); }
    }

    .floating-heart {
      position: absolute;
      font-size: 20px;
      color: #ff4d6d;
      opacity: 0.7;
      animation: floatUp 4s linear forwards;
      z-index: 1;
      pointer-events: none;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-150vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="envelope" id="envelope" onclick="openEnvelope()">
    <div class="flap"></div>
    <div class="card">
      <h2>Dear Friend 💖</h2>
      <div class="scroll-area">
        <p>
          On this special Friendship Day, I want to celebrate the beautiful bond we share. You’ve been there through all my ups and downs — offering kindness, strength, and unwavering support when I needed it most.
          <br><br>
          In a world that often feels too busy, too loud, or too uncertain, you’ve been a calm and constant light. Your respect, honesty, and love are treasures I never take for granted.
          <br><br>
          Thank you for the laughter, the deep talks, the inside jokes, and the silent understanding. You’ve touched my life in more ways than words can express. You are more than a friend — you are family.Friendship is the golden thread that ties our hearts together even when miles apart. On this Friendship Day, I celebrate the laughter we’ve shared, the secrets we’ve kept, and the comfort we’ve found in each other’s presence. True friends are rare, and I feel incredibly lucky to have you — someone who listens without judgment, stands by me without conditions, and brings light even in the darkest times. Here’s to the bond that grows stronger with every memory. 
          Happy Friendship Day! 💫💕 love you💕
          
        </p>
      </div>
    </div>
  </div>

  <div class="footer">
    Click the <span class="heart">💌</span> to open your Friendship message.
  </div>

  <script>
    function openEnvelope() {
      const envelope = document.getElementById('envelope');
      if (!envelope.classList.contains('open')) {
        envelope.classList.add('open');
        launchManyHearts(120);
      }
    }

    function launchManyHearts(count) {
      for (let i = 0; i < count; i++) {
        const heart = document.createElement('div');
        heart.className = 'floating-heart';
        heart.innerText = '💖';
        heart.style.left = Math.random() * window.innerWidth + 'px';
        heart.style.top = window.innerHeight + 'px';
        heart.style.fontSize = (12 + Math.random() * 28) + 'px';
        heart.style.animationDuration = (3 + Math.random() * 2) + 's';
        heart.style.animationDelay = (Math.random() * 2) + 's';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 6000);
      }
    }
  </script>

</body>
</html>
