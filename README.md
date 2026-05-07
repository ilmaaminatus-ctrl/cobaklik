<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Good Night 🌙</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: radial-gradient(ellipse at bottom, #1B2735 0%, #090A0F 100%);
      font-family: 'Arial', sans-serif;
      overflow: hidden;
      position: relative;
    }

    .stars {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 0;
    }

    .star {
      position: absolute;
      background: white;
      border-radius: 50%;
      opacity: 0.5;
      animation: twinkle var(--duration) infinite ease-in-out;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.3; transform: scale(1); }
      50% { opacity: 1; transform: scale(1.2); }
    }

    .card {
      position: relative;
      z-index: 1;
      width: 85%;
      max-width: 350px;
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(15px);
      -webkit-backdrop-filter: blur(15px);
      border-radius: 25px;
      padding: 30px 20px;
      text-align: center;
      color: white;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.5s ease;
    }

    h1 {
      font-size: 22px;
      min-height: 100px;
      display: flex;
      align-items: center;
      justify-content: center;
      line-height: 1.5;
      transition: opacity 0.4s ease;
    }

    button {
      border: none;
      padding: 12px 35px;
      border-radius: 50px;
      background: white;
      color: #1e1e2f;
      font-weight: bold;
      font-size: 16px;
      cursor: pointer;
      margin-top: 20px;
      box-shadow: 0 4px 15px rgba(255,255,255,0.2);
    }

    img {
      width: 200px;
      height: 200px;
      object-fit: cover;
      border-radius: 20px;
      margin-top: 15px;
      display: none;
      animation: fadeIn 1s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .moon {
      position: absolute;
      top: 40px;
      right: 40px;
      font-size: 50px;
      animation: float 3s infinite ease-in-out;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-15px); }
    }
  </style>
</head>
<body>

<div class="stars" id="starContainer"></div>
<div class="moon">🌙</div>

<div class="card">
  <h1 id="text">Haii</h1>
  <img id="meme" src="https://raw.githubusercontent.com/ilmaaminatus-ctrl/cobaklik/refs/heads/main/aa99d98250a5d0dc22341679d1450be1.jpg" alt="sleepy">
  <button onclick="nextText()" id="btn">Next ✨</button>
</div>

<script>
  const container = document.getElementById('starContainer');
  for (let i = 0; i < 100; i++) {
    const star = document.createElement('div');
    star.className = 'star';
    const size = Math.random() * 3 + 'px';
    star.style.width = size;
    star.style.height = size;
    star.style.top = Math.random() * 100 + '%';
    star.style.left = Math.random() * 100 + '%';
    star.style.setProperty('--duration', Math.random() * 3 + 2 + 's');
    container.appendChild(star);
  }

  const texts = [
    "Haii",
    "Pengumuman penting",
    "Aku resmi mengundurkan diri",
    "Dari dunia sadar untuk sementara",
    "Karena kasur sudah memanggil dengan tulus",
    "Bantal juga sudah menunggu",
    "Selimut siap menyambut",
    "Jadi aku pamit dulu",
    "Besok kita lanjut hidup lagi",
    "Good night 😴",
    "Terima kasih sudah membuka link inii 🤍"
  ];

  let index = 0;

  function nextText() {
    index++;
    const textElement = document.getElementById("text");
    const btn = document.getElementById("btn");
    const meme = document.getElementById("meme");

    if (index < texts.length) {
      textElement.style.opacity = 0;
      setTimeout(() => {
        textElement.innerText = texts[index];
        textElement.style.opacity = 1;
        if (index >= 9) { 
          meme.style.display = "inline-block";
        }
      }, 400);
    } else {
      textElement.innerText = "Selesaiii 🌙";
      btn.style.display = "none";
    }
  }
</script>

</body>
</html>
