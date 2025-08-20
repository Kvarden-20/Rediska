<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>👾 REDISKA 👾</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, sans-serif;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      color: #fff;
      overflow: hidden;
      background: linear-gradient(270deg, #1e1e2f, #2c2c54, #1e1e2f);
      background-size: 600% 600%;
      animation: gradientBG 20s ease infinite;
    }

    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    h1 {
      margin-bottom: 50px;
      font-size: 2.8rem;
      text-align: center;
      animation: glow 2s infinite alternate;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #0ff, 0 0 20px #0ff; }
      to { text-shadow: 0 0 20px #ff00ff, 0 0 30px #ff00ff; }
    }

    .links {
      display: flex;
      flex-direction: column;
      gap: 20px;
      width: 90%;
      max-width: 400px;
      z-index: 2;
      position: relative;
    }

    .links a {
      text-decoration: none;
      color: white;
      font-size: 1.2rem;
      padding: 15px 25px;
      border-radius: 12px;
      display: flex;
      align-items: center;
      gap: 12px;
      background: rgba(255,255,255,0.1);
      transition: transform 0.3s, background 0.3s, box-shadow 0.3s;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeInUp 0.6s forwards;
    }

    .links a:hover {
      transform: scale(1.08);
      background: rgba(255,255,255,0.25);
      box-shadow: 0 0 15px #0ff, 0 0 25px #ff00ff;
    }

    .links a:hover img.icon {
      filter: drop-shadow(0 0 12px #0ff);
    }

    img.icon {
      width: 28px;
      height: 28px;
      transition: filter 0.3s;
    }

    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Задержки появления ссылок */
    .links a:nth-child(1) { animation-delay: 0.2s; }
    .links a:nth-child(2) { animation-delay: 0.4s; }
    .links a:nth-child(3) { animation-delay: 0.6s; }
    .links a:nth-child(4) { animation-delay: 0.8s; }
    .links a:nth-child(5) { animation-delay: 1s; }
    .links a:nth-child(6) { animation-delay: 1.2s; }

    /* Частицы */
    .particle {
      position: absolute;
      border-radius: 50%;
      background: rgba(255,255,255,0.2);
      pointer-events: none;
      will-change: transform;
      box-shadow: 0 0 6px rgba(255,255,255,0.5);
    }
  </style>
</head>
<body>

  <h1>👾 REDISKA 👾</h1>

  <div class="links">
    <a href="https://t.me/KvRediska" target="_blank">
      <img class="icon" src="https://cdn-icons-png.flaticon.com/512/2111/2111646.png" alt="Telegram">
      REDISKA (tgk)
    </a>

    <a href="https://youtube.com/@kvarden_rd?si=cIdl03GINs0-V4sG" target="_blank">
      <img class="icon" src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="YouTube">
      KVARDEN
    </a>

    <a href="https://t.me/kvardanYU" target="_blank">
      <img class="icon" src="https://cdn-icons-png.flaticon.com/512/727/727245.png" alt="Music">
      music
    </a>

    <a href="https://t.me/music_kvarden" target="_blank">
      <img class="icon" src="https://cdn-icons-png.flaticon.com/512/727/727245.png" alt="Music²">
      music²
    </a>

    <a href="https://t.me/chatKEMVAR" target="_blank">
      <img class="icon" src="https://cdn-icons-png.flaticon.com/512/5968/5968267.png" alt="Minecraft">
      Minecraft chat (KEMVAR)
    </a>

    <a href="https://discord.gg/wwkSa8jy" target="_blank">
      <img class="icon" src="https://cdn-icons-png.flaticon.com/512/2111/2111370.png" alt="Discord">
      Discord
    </a>
  </div>

  <!-- Частицы -->
  <script>
    const numParticles = 50;
    const particles = [];
for(let i=0; i<numParticles; i++){
      const p = document.createElement('div');
      p.classList.add('particle');
      const size = Math.random() * 5 + 2;
      p.style.width = size + 'px';
      p.style.height = size + 'px';
      p.style.left = Math.random() * window.innerWidth + 'px';
      p.style.top = Math.random() * window.innerHeight + 'px';
      p.speedX = (Math.random() - 0.5) * 0.3;
      p.speedY = (Math.random() - 0.5) * 0.3;
      document.body.appendChild(p);
      particles.push(p);
    }

    document.addEventListener('mousemove', e => {
      const mouseX = e.clientX;
      const mouseY = e.clientY;
      particles.forEach(p => {
        const dx = mouseX - parseFloat(p.style.left);
        const dy = mouseY - parseFloat(p.style.top);
        p.style.transform = translate(${dx * 0.03}px, ${dy * 0.03}px);
      });
    });

    function animateParticles(){
      particles.forEach(p => {
        let x = parseFloat(p.style.left) + p.speedX;
        let y = parseFloat(p.style.top) + p.speedY;

        if(x < 0) { x = window.innerWidth; }
        if(x > window.innerWidth) { x = 0; }
        if(y < 0) { y = window.innerHeight; }
        if(y > window.innerHeight) { y = 0; }

        p.style.left = x + 'px';
        p.style.top = y + 'px';
      });
      requestAnimationFrame(animateParticles);
    }

    animateParticles();
  </script>

</body>
</html> 
<footer>© REDISKA 2025</footer>

<style>
footer {
  position: fixed;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  color: #fff;
  font-size: 0.9rem;
  opacity: 0.9;
  pointer-events: none;
  animation: glowFooter 2s infinite alternate;
}

@keyframes glowFooter {
  from {
    text-shadow: 0 0 5px #0ff, 0 0 10px #0ff;
  }
  to {
    text-shadow: 0 0 15px #ff00ff, 0 0 25px #ff00ff;
  }
}
</style>
