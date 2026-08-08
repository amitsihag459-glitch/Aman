<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>A Special Surprise for You! 🎂</title>
  
  <!-- Fonts & Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600&family=Great+Vibes&family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: radial-gradient(circle, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
      color: #fff;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow-x: hidden;
    }

    /* Phase Containers */
    .phase {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      width: 100%;
      max-width: 800px;
      padding: 2rem;
      animation: fadeIn 1s ease-in-out forwards;
    }

    .phase.active {
      display: flex;
    }

    /* Phase 1: Interactive Gift Box */
    .gift-container {
      cursor: pointer;
      margin-top: 2rem;
      transition: transform 0.3s ease;
    }

    .gift-container:hover {
      transform: scale(1.05);
    }

    .gift-box {
      font-size: 8rem;
      animation: pulse 1.5s infinite alternate;
      user-select: none;
    }

    .instruction {
      font-size: 1.2rem;
      color: #ff75a0;
      margin-top: 1rem;
      font-weight: 600;
      letter-spacing: 1px;
    }

    /* Phase 2: Celebration Content */
    .title {
      font-family: 'Great Vibes', cursive;
      font-size: 4.5rem;
      color: #fbd46d;
      text-shadow: 0 0 20px rgba(251, 212, 109, 0.5);
      margin-bottom: 1rem;
    }

    .card {
      background: rgba(255, 255, 255, 0.08);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.15);
      border-radius: 20px;
      padding: 2.5rem;
      box-shadow: 0 20px 40px rgba(0,0,0,0.4);
      margin: 1.5rem 0;
      max-width: 600px;
    }

    .message {
      font-family: 'Caveat', cursive;
      font-size: 2rem;
      line-height: 1.4;
      color: #e2e8f0;
    }

    /* Interactive Buttons */
    .btn {
      background: linear-gradient(135deg, #ff4b2b, #ff416c);
      color: white;
      border: none;
      padding: 0.9rem 2rem;
      font-size: 1.1rem;
      font-weight: 600;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 10px 20px rgba(255, 65, 108, 0.4);
      transition: all 0.3s ease;
      margin-top: 1.5rem;
    }

    .btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 15px 25px rgba(255, 65, 108, 0.6);
    }

    /* Floating Balloons Background */
    .balloon {
      position: absolute;
      bottom: -100px;
      opacity: 0.7;
      animation: floatUp 8s linear infinite;
      z-index: 0;
      pointer-events: none;
    }

    /* Keyframe Animations */
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes pulse {
      0% { transform: scale(1) rotate(-3deg); }
      100% { transform: scale(1.1) rotate(3deg); }
    }

    @keyframes floatUp {
      0% { transform: translateY(0) rotate(0deg); opacity: 0.8; }
      100% { transform: translateY(-120vh) rotate(360deg); opacity: 0; }
    }
  </style>
</head>
<body>

  <!-- Phase 1: Mysterious Gift Box -->
  <div id="phase1" class="phase active">
    <h2 style="font-size: 2rem; color: #e2e8f0;">Someone sent you a surprise...</h2>
    <div class="gift-container" onclick="openSurprise()">
      <div class="gift-box">🎁</div>
    </div>
    <p class="instruction">Tap the gift box to open!</p>
  </div>

  <!-- Phase 2: Celebration & Message Reveal -->
  <div id="phase2" class="phase">
    <h1 class="title">Happy Birthday! 🎉</h1>
    
    <div class="card">
      <p class="message">
        "Wishing you a day filled with laughter, joy, and unforgettable moments. May this coming year bring you success, adventure, and all the happiness in the world!" ✨
      </p>
    </div>

    <button class="btn" onclick="triggerFireworks()">Celebrate Again! 🎆</button>
  </div>

  <script>
    // Reveal Phase 2 & trigger celebration sound and confetti
    function openSurprise() {
      document.getElementById('phase1').classList.remove('active');
      document.getElementById('phase2').classList.add('active');

      // Launch Confetti
      triggerFireworks();
      
      // Spawn floating background balloons
      createBalloons();
    }

    // Confetti Fireworks Effect
    function triggerFireworks() {
      const count = 200;
      const defaults = { origin: { y: 0.7 } };

      function fire(particleRatio, opts) {
        confetti(Object.assign({}, defaults, opts, {
          particleCount: Math.floor(count * particleRatio)
        }));
      }

      fire(0.25, { spread: 26, startVelocity: 55 });
      fire(0.2, { spread: 60 });
      fire(0.35, { spread: 100, decay: 0.91, scalar: 0.8 });
      fire(0.1, { spread: 120, startVelocity: 25, decay: 0.92, scalar: 1.2 });
      fire(0.1, { spread: 120, startVelocity: 45 });
    }

    // Create floating balloon emojis
    function createBalloons() {
      const balloonEmojis = ['🎈', '🎉', '✨', '⭐'];
      for (let i = 0; i < 15; i++) {
        const balloon = document.createElement('div');
        balloon.className = 'balloon';
        balloon.innerText = balloonEmojis[Math.floor(Math.random() * balloonEmojis.length)];
        balloon.style.left = Math.random() * 100 + 'vw';
        balloon.style.fontSize = (Math.random() * 20 + 24) + 'px';
        balloon.style.animationDuration = (Math.random() * 4 + 6) + 's';
        balloon.style.animationDelay = (Math.random() * 3) + 's';
        document.body.appendChild(balloon);
      }
    }
  </script>
</body>
</html>
