# untuk-perempuan-yang-anonim-itu
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Untukmu</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      font-family: 'Georgia', serif;
      background: linear-gradient(135deg, #f9f6f2, #fde2ea);
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    .card {
      background: white;
      padding: 40px;
      max-width: 520px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      animation: fadeIn 2s ease;
    }

    h1 {
      color: #c94f7c;
      margin-bottom: 20px;
    }

    .poem {
      font-size: 18px;
      line-height: 1.8;
      color: #333;
      margin-bottom: 30px;
      white-space: pre-line;
    }

    button {
      background: #c94f7c;
      color: white;
      border: none;
      padding: 12px 25px;
      border-radius: 25px;
      font-size: 16px;
      cursor: pointer;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }
  </style>
</head>

<body>

  <div class="card">
    <h1>Untukmu 🌹</h1>

    <div class="poem">
Aku pernah patah,
bukan karena cinta itu salah,
tapi karena aku terlalu percaya
pada hal yang belum tentu tinggal.

Sejak itu aku belajar menahan,
bukan menutup.
Belajar menjaga hati,
bukan memenjarakannya.

Jika suatu hari
kamu datang tanpa memaksa,
hadir tanpa janji berlebihan,
dan membuatku bahagia dengan cara sederhana,
mungkin aku akan berani lagi,
bukan untuk jatuh,
tapi untuk percaya.
    </div>

    <button id="playBtn">▶ Putar Musik</button>
  </div>

  <!-- AUDIO -->
  <audio id="music" preload="auto">
    <source src="musik.mp3" type="audio/mpeg">
  </audio>

  <script>
    const music = document.getElementById("music");
    const btn = document.getElementById("playBtn");
    let unlocked = false;

    btn.addEventListener("click", async () => {
      try {
        if (!unlocked) {
          // Unlock audio context
          await music.play();
          unlocked = true;
          btn.innerText = "⏸ Hentikan Musik";
        } else if (music.paused) {
          music.play();
          btn.innerText = "⏸ Hentikan Musik";
        } else {
          music.pause();
          btn.innerText = "▶ Putar Musik";
        }
      } catch (e) {
        alert("Klik sekali lagi untuk memulai musik 🎵");
      }
    });
  </script>

</body>
</html>
