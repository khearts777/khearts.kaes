# khearts.kaes
title<khearts fan page>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Khearts Fan Page</title>
  <style>
    body { font-family: Arial, sans-serif; background: #fdf6f9; margin: 0; }
    header { background: #ff99cc; color: white; padding: 20px; text-align: center; }
    nav a { margin: 0 15px; color: white; text-decoration: none; font-weight: bold; }
    section { padding: 40px; }
    .members { display: flex; justify-content: space-around; flex-wrap: wrap; }
    .member { background: white; border-radius: 10px; padding: 20px; margin: 10px; width: 200px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
    .shop-item { display: inline-block; margin: 20px; padding: 20px; background: #fff; border-radius: 10px; }
    #countdown { font-size: 24px; font-weight: bold; color: #cc0066; }
  </style>
</head>
<body>
  <header>
    <h1>✨ Welcome to Khearts ✨</h1>
    <nav>
      <a href="#home">Home</a>
      <a href="#members">Members</a>
      <a href="#avatar">Avatar</a>
      <a href="#shop">Shop</a>
    </nav>
  </header>

  <section id="home">
    <h2>Debut Countdown</h2>
    <p>We debut in <span id="countdown"></span> days!</p>
  </section>

  <section id="members">
    <h2>Meet the Members</h2>
    <div class="members">
      <div class="member">
        <h3>Karlyn</h3>
        <p>Leader, Main Rapper, Sub Vocalist, Lead Dancer</p>
      </div>
      <div class="member">
        <h3>Alyssa</h3>
        <p>Maknae, Visual, Main Vocalist, Sub Dancer</p>
      </div>
      <div class="member">
        <h3>Trixie</h3>
        <p>Main Dancer, Lead Rapper, Sub Vocalist, Center</p>
      </div>
      <div class="member">
        <h3>Hayley</h3>
        <p>Lead Vocalist, Lead Rapper, Lead Dancer</p>
      </div>
    </div>
  </section>

  <section id="avatar">
    <h2>Customize Your Avatar</h2>
    <p>Pick your style and colors!</p>
    <canvas id="avatarCanvas" width="200" height="200" style="border:1px solid #ccc;"></canvas><br>
    <button onclick="changeAvatarColor()">Change Color</button>
  </section>

  <section id="shop">
    <h2>Shop Cute Outfits</h2>
    <div class="shop-item">🎀 Pink Dress</div>
    <div class="shop-item">👟 Sneakers</div>
    <div class="shop-item">👜 Tote Bag</div>
  </section>

  <script>
    // Countdown
    const debutDays = 40;
    document.getElementById("countdown").textContent = debutDays;

    // Avatar customization
    const canvas = document.getElementById("avatarCanvas");
    const ctx = canvas.getContext("2d");
    ctx.fillStyle = "#ff99cc";
    ctx.fillRect(50, 50, 100, 100);

    function changeAvatarColor() {
      const colors = ["#ff99cc", "#99ccff", "#ccff99", "#ffcc99"];
      const randomColor = colors[Math.floor(Math.random() * colors.length)];
      ctx.fillStyle = randomColor;
      ctx.fillRect(50, 50, 100, 100);
    }
  </script>
</body>
</html>
<section id="fanboard">
  <h2>Fan Message Board 💖</h2>
  <p>Leave your love and support for Khearts!</p>
  
  <textarea id="fanMessage" rows="4" cols="50" placeholder="Write your message here..."></textarea><br>
  <button onclick="postMessage()">Post Message</button>
  
  <div id="messages" style="margin-top:20px; background:#fff; padding:20px; border-radius:10px;">
    <h3>Messages from Fans:</h3>
    <ul id="messageList"></ul>
  </div>
</section>

<script>
  function postMessage() {
    const messageBox = document.getElementById("fanMessage");
    const message = messageBox.value.trim();
    if (message) {
      const list = document.getElementById("messageList");
      const newItem = document.createElement("li");
      newItem.textContent = message;
      list.appendChild(newItem);
      messageBox.value = "";
    } else {
      alert("Please write a message before posting!");
    }
  }
</script>

<section id="fanboard">
  <h2>Fan Message Board 💖</h2>
  <p>Leave your love and support for Khearts!</p>
  
  <textarea id="fanMessage" rows="4" cols="50" placeholder="Write your message here..."></textarea><br>
  <button onclick="postMessage()">Post Message</button>
  
  <div id="messages" style="margin-top:20px;">
    <h3>Messages from Fans:</h3>
    <ul id="messageList"></ul>
  </div>
</section>

<section id="coins">
  <h2>✨ Your Coins ✨</h2>
  <p>You currently have <span id="coinCount">0</span> coins.</p>
</section>

<style>
  #fanboard textarea {
    border: 2px solid #ff99cc;
    border-radius: 10px;
    padding: 10px;
    font-family: 'Comic Sans MS', cursive;
    background: #fff0f6;
  }
  #fanboard button {
    background: #ff66b2;
    color: white;
    border: none;
    padding: 10px 20px;
    margin-top: 10px;
    border-radius: 20px;
    cursor: pointer;
    font-weight: bold;
  }
  #fanboard button:hover {
    background: #cc0066;
  }
  #messageList li {
    list-style: none;
    background: #ffe6f2;
    margin: 10px 0;
    padding: 15px;
    border-radius: 15px;
    box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
    font-family: 'Trebuchet MS', sans-serif;
    position: relative;
  }
  #messageList li::before {
    content: "💌";
    position: absolute;
    left: -30px;
    top: 10px;
    font-size: 20px;
  }
  #coins {
    background: #fff0f6;
    padding: 20px;
    border-radius: 15px;
    margin-top: 30px;
    text-align: center;
    font-size: 18px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  }
</style>

<script>
  let coins = 0;

  function postMessage() {
    const messageBox = document.getElementById("fanMessage");
    const message = messageBox.value.trim();
    if (message) {
      const list = document.getElementById("messageList");
      const newItem = document.createElement("li");
      newItem.textContent = message;
      list.appendChild(newItem);
      messageBox.value = "";

      // Earn coins for posting
      coins += 5;
      document.getElementById("coinCount").textContent = coins;
    } else {
      alert("Please write a message before posting!");
    }
  }
</script>
