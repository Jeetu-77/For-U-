<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>For Someone Special 💖</title>
  <style>
    * {margin: 0; padding: 0; box-sizing: border-box;}
    body {
      background: linear-gradient(to top right, #ffe3e3, #cceeff);
      height: 100vh;
      overflow: hidden;
      font-family: 'Segoe UI', sans-serif;
      position: relative;
    }

    .click-here {
      position: absolute;
      top: 40%;
      left: 50%;
      transform: translate(-50%, -50%);
      color: #fff;
      font-size: 2rem;
      text-shadow: 0 0 10px #ff69b4;
      animation: glow 2s ease-in-out infinite alternate;
      cursor: pointer;
      z-index: 10;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #ff69b4; }
      to { text-shadow: 0 0 20px #ff1493; }
    }

    .message {
      position: absolute;
      top: 60%;
      left: 50%;
      transform: translateX(-50%);
      color: #fff;
      font-size: 1.5rem;
      max-width: 80%;
      text-align: center;
      opacity: 0;
      transition: opacity 2s ease-in-out;
      text-shadow: 0 0 5px #ff69b4;
      z-index: 10;
    }

    .show { opacity: 1; }

    .object {
      position: absolute;
      background-repeat: no-repeat;
      background-size: contain;
      pointer-events: none;
    }

    .leaf {
      width: 30px;
      height: 30px;
      background-image: url('https://i.postimg.cc/TwYrz2kK/leaf.png');
      animation: fall 10s linear infinite;
      opacity: 0.6;
    }

    @keyframes fall {
      0% {transform: translateY(0) rotate(0);}
      100% {transform: translateY(100vh) rotate(360deg);}
    }

    .butterfly {
      width: 50px;
      height: 50px;
      background-image: url('https://i.postimg.cc/VLJp5LDb/butterfly.png');
      animation: fly 12s linear infinite;
    }

    @keyframes fly {
      0% {transform: translateY(100vh) rotate(0);}
      100% {transform: translateY(-100vh) rotate(360deg);}
    }

    .bird {
      width: 60px;
      height: 60px;
      background-image: url('https://i.postimg.cc/Y0YBBtHt/bird.png');
      animation: flyBird 20s linear infinite;
    }

    @keyframes flyBird {
      0% { left: -60px; top: 20vh;}
      100% { left: 110%; top: 25vh;}
    }

    .tree {
      width: 180px;
      height: 250px;
      background-image: url('https://i.postimg.cc/MKmM4mpy/tree.png');
      bottom: 0;
      left: 20px;
    }

    .cat {
      width: 80px;
      height: 80px;
      background-image: url('https://i.postimg.cc/Jn0NmTn9/cat.png');
      bottom: 0;
      left: 80px;
    }

    .ground-object {
      position: absolute;
      background-size: contain;
      background-repeat: no-repeat;
      z-index: 1;
    }

    footer {
      position: absolute;
      bottom: 10px;
      width: 100%;
      text-align: center;
      color: #fff;
      font-size: 1rem;
      text-shadow: 0 0 5px #ff1493;
    }
  </style>
</head>
<body>

  <div class="click-here" onclick="revealMessage()">Click here for a magical surprise ✨</div>
  <div class="message" id="message">"You're the soft wind to my soul, the beauty in my sky, and the dream I never want to wake up from. 🌸"</div>

  <!-- Static Tree & Cat -->
  <div class="ground-object tree"></div>
  <div class="ground-object cat"></div>

  <!-- Flying Birds -->
  <div class="object bird" style="top: 20vh; left: 0;"></div>

  <footer>Made with 💖 just for you</footer>

  <script>
    function revealMessage() {
      document.getElementById('message').classList.add('show');
    }

    function createFlyingObject(className, limit = 100) {
      const el = document.createElement("div");
      el.className = `object ${className}`;
      el.style.left = Math.random() * limit + "vw";
      el.style.top = "-50px";
      el.style.animationDuration = 5 + Math.random() * 10 + "s";
      el.style.transform = `scale(${0.5 + Math.random()})`;
      document.body.appendChild(el);
      setTimeout(() => el.remove(), 15000);
    }

    // Generate leaves and butterflies every second
    setInterval(() => {
      createFlyingObject("leaf");
      if (Math.random() > 0.5) createFlyingObject("butterfly");
    }, 1000);
  </script>

</body>
</html>
