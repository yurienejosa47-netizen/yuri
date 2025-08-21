<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>myloveofmylife</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom right, pink, lightyellow);
      background-size: cover;
      overflow-x: hidden;
      overflow-y: auto;
    }

    /* Top menu */
    .navbar {
      background-color: #ffb6c1;
      overflow: hidden;
      display: flex;
      justify-content: center;
      box-shadow: 0 4px 6px rgba(0,0,0,0.2);
      position: sticky;
      top: 0;
      z-index: 50;
    }
    .navbar a {
      display: block;
      color: #663300;
      text-align: center;
      padding: 14px 20px;
      text-decoration: none;
      font-weight: bold;
      cursor: pointer;
    }
    .navbar a:hover {
      background-color: #ffd700;
      color: #cc0052;
    }

    /* Content */
    .content {
      text-align: center;
      margin-top: 60px;
      font-size: 28px;
      color: #660033;
      font-weight: bold;
    }

    /* Envelope */
    .envelope {
      width: 300px;
      height: 200px;
      background: #fff0f5;
      margin: 60px auto;
      position: relative;
      border: 2px solid #ff99cc;
      border-radius: 6px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.3);
      cursor: pointer;
      transition: transform 0.2s ease-in-out;
      z-index: 10;
    }
    .envelope:hover {
      transform: scale(1.05);
    }
    .envelope:before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 0;
      border-left: 150px solid transparent;
      border-right: 150px solid transparent;
      border-top: 100px solid #ffccff;
    }

    /* Heart design on envelope */
    .envelope-heart {
      position: absolute;
      top: 70px;
      left: 50%;
      transform: translateX(-50%) rotate(-45deg);
      width: 40px;
      height: 40px;
      background: red;
    }
    .envelope-heart:before, .envelope-heart:after {
      content: "";
      position: absolute;
      width: 40px;
      height: 40px;
      background: red;
      border-radius: 50%;
    }
    .envelope-heart:before { top: -20px; left: 0; }
    .envelope-heart:after { left: 20px; top: 0; }

    /* Floating Hearts */
    .floating-heart {
      position: absolute;
      bottom: -50px;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(-45deg);
      animation: floatUp 8s infinite ease-in-out;
    }
    .floating-heart:before, .floating-heart:after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }
    .floating-heart:before { top: -10px; left: 0; }
    .floating-heart:after { left: 10px; top: 0; }

    @keyframes floatUp {
      0% { transform: translateY(0) rotate(-45deg); opacity: 1; }
      100% { transform: translateY(-600px) rotate(-45deg); opacity: 0; }
    }

    /* Popup */
    .popup {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      justify-content: center;
      align-items: center;
      z-index: 20;
    }
    .popup-content {
      background-color: #fff;
      padding: 30px;
      border-radius: 10px;
      text-align: center;
      position: relative;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }
    .popup-content p {
      font-size: 1.5em;
      margin-bottom: 20px;
      color: #333;
    }
    .popup-content button {
      padding: 10px 20px;
      font-size: 1em;
      margin: 0 10px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    .popup-content button.yes-btn {
      background-color: #ff69b4;
      color: white;
    }
    .popup-content button.yes-btn:hover { background-color: #ff1493; }
    .popup-content button.no-btn {
      background-color: #e0e0e0;
      color: #333;
    }
    .popup-content button.no-btn:hover { background-color: #c0c0c0; }
    .close-btn {
      position: absolute;
      top: 10px;
      right: 10px;
      background: none;
      border: none;
      font-size: 1.2em;
      cursor: pointer;
      color: #aaa;
    }

    /* Side Images */
    .side-images {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 40px;
    }
    .side {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }
    .side img {
      width: 180px;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>
  <div class="navbar">
    <a href="Things you like.html">Your favorite</a>
    <a href="Mga masasaya nating ala ala na hindi na maibabalik pa.html">Mga masasaya nating ala ala</a>
  </div>

  <div class="content">
    <p id="main-text">Click mo po</p>
  </div>

  <div class="side-images">
    <div class="side left">
      <img src="https://via.placeholder.com/180" alt="Image 1">
      <img src="https://via.placeholder.com/180" alt="Image 2">
    </div>

    <!-- Envelope (Clickable) -->
    <div class="envelope" onclick="openEnvelope()">
      <div class="envelope-heart"></div>
    </div>

    <div class="side right">
      <img src="https://via.placeholder.com/180" alt="Image 3">
      <img src="https://via.placeholder.com/180" alt="Image 4">
    </div>
  </div>

  <!-- Floating hearts -->
  <div class="floating-heart" style="left:10%; animation-delay:0s;"></div>
  <div class="floating-heart" style="left:30%; animation-delay:2s;"></div>
  <div class="floating-heart" style="left:50%; animation-delay:4s;"></div>
  <div class="floating-heart" style="left:70%; animation-delay:1s;"></div>
  <div class="floating-heart" style="left:90%; animation-delay:3s;"></div>

  <!-- Popup -->
  <div class="popup" id="popup">
    <div class="popup-content">
      <button class="close-btn" onclick="closePopup()">X</button>
      <p>Do you still love me?</p>

      <form action="https://formspree.io/f/mdkdrvee" method="POST" id="answerForm">
        <input type="hidden" name="answer" id="answerInput">
      </form>

      <button class="yes-btn" onclick="submitAnswer('Yes')">Yes</button>
      <button class="no-btn" onclick="submitAnswer('No')">No</button>
    </div>
  </div>

  <script>
    function openEnvelope() {
      document.getElementById("popup").style.display = "flex";
    }

    function closePopup() {
      document.getElementById("popup").style.display = "none";
    }

    function submitAnswer(ans) {
      // put the answer into hidden field
      document.getElementById("answerInput").value = ans;

      // submit the form
      document.getElementById("answerForm").submit();

      // redirect after small delay
      setTimeout(function() {
        if (ans === "Yes") {
          window.location.href = "yes.html"; // 👉 create this file
        } else {
          window.location.href = "no.html"; // 👉 create this file
        }
      }, 500);
    }
  </script>
</body>
</html>
