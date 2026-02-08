# sanvalentin-
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Para Ti ❤️</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: radial-gradient(circle at top, #ffb6c1, #ff4d6d);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      font-family: 'Arial', sans-serif;
      overflow: hidden;
      text-align: center;
      padding: 20px;
    }

    h1 {
      color: white;
      font-size: 2.2rem;
      margin-bottom: 25px;
      text-shadow: 0 3px 10px rgba(0,0,0,0.3);
    }

    .buttons {
      display: flex;
      gap: 20px;
      margin-top: 10px;
    }

    button {
      padding: 15px 30px;
      font-size: 1.2rem;
      border: none;
      border-radius: 40px;
      cursor: pointer;
    }

    .yes {
      background: white;
      color: #ff4d6d;
      font-weight: bold;
    }

    .no {
      background: #ddd;
      color: #555;
    }

    .message {
      display: none;
      margin-top: 30px;
      font-size: 1.8rem;
      color: white;
      animation: fadeIn 2s ease forwards;
      text-shadow: 0 3px 10px rgba(0,0,0,0.3);
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }

    .heart {
      position: absolute;
      color: red;
      animation: float 4s linear infinite;
      opacity: 0.8;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) scale(1);
      }
      100% {
        transform: translateY(-10vh) scale(1.6);
      }
    }
  </style>
</head>

<body>

  <h1>¿Quieres ser mi San Valentín? ❤️</h1>

  <div class="buttons">
    <button class="yes" onclick="yesClick()">Sí</button>
    <button class="no">No</button>
  </div>

  <div class="message" id="finalMessage">
    💖 Sabía que dirías que sí 💖
  </div>

  <audio id="music">
    <source src="princesa.mp3" type="audio/mpeg">
  </audio>

  <script>
    function yesClick() {
      document.querySelector(".buttons").style.display = "none";
      document.getElementById("finalMessage").style.display = "block";
      document.getElementById("music").play();

      setInterval(createHeart, 180);
    }

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = (Math.random() * 20 + 20) + "px";
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 4000);
    }
  </script>

</body>
</html>
