<!DOCTYPE html>
<html>
<head>
  <title>Happy Birthday 💖</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      font-family: Arial, sans-serif;
      background: linear-gradient(45deg, #ff69b4, #ffb6c1, #ff69b4);
      background-size: 300% 300%;
      animation: bg 6s infinite alternate;
      overflow: hidden;
    }

    @keyframes bg {
      0% { background-position: 0% 50%; }
      100% { background-position: 100% 50%; }
    }

    .card {
      background: rgba(255,255,255,.9);
      padding: 35px;
      border-radius: 25px;
      box-shadow: 0 10px 30px rgba(0,0,0,.2);
    }

    h1 { color: #e91e63; }
    p { color: #444; }

    .heart {
      position: fixed;
      font-size: 30px;
      animation: float 5s linear infinite;
    }

    .red { color: red; }
    .blue { color: blue; }

    @keyframes float {
      from { transform: translateY(110vh) rotate(0deg); }
      to { transform: translateY(-120vh) rotate(360deg); }
    }
  </style>
</head>

<body>
  <div class="card">
    <h1>🎂 Happy Birthday, Bestie! 💖</h1>
    <p>Wishing you endless happiness, love & beautiful memories! 🥳✨</p>
    <p>You're truly one of a kind! ❤️</p>
  </div>

  <div class="heart red" style="left:10%; animation-delay:0s;">♥</div>
  <div class="heart blue" style="left:30%; animation-delay:1s;">♥</div>
  <div class="heart red" style="left:50%; animation-delay:2s;">♥</div>
  <div class="heart blue" style="left:70%; animation-delay:3s;">♥</div>
  <div class="heart red" style="left:90%; animation-delay:4s;">♥</div>
</body>
</html>


