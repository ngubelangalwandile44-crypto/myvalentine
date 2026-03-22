<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Will You Be My girlfriend?</title>
<style>
    body {
        margin: 0;
        height: 100vh;
        background: linear-gradient(to bottom right, #ff4d6d, #ffc2d1);
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: Arial, sans-serif;
        overflow: hidden;
    }
    .card {
        background: #fff0f5;
        width: 90%;
        max-width: 420px;
        padding: 30px;
        border-radius: 30px;
        text-align: center;
        box-shadow: 0 15px 40px rgba(0,0,0,0.3);
    }
    h1 { color: #d6336c; }
    h2 { color: #b5179e; }
    p {
        font-size: 18px;
        color: #444;
    }
    /* BUTTON ROW */
    .buttons {
        margin-top: 30px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: relative;
    }
    button {
        width: 140px;          /* FIXED SIZE */
        padding: 12px 0;
        font-size: 18px;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        transition: transform 0.15s ease;
    }
    #yesBtn {
        background-color: #ff4d6d;
        color: white;
    }
    #yesBtn:hover {
        background-color: #e63950;
    }
    #noBtn {
        background-color: #adb5bd;
        color: white;
        position: relative; /* IMPORTANT */
    }
    /* Falling hearts */
    .heart {
        position: fixed;
        font-size: 20px;
        animation: fall 4s linear infinite;
        z-index: 1;
    }
    @keyframes fall {
        0% { transform: translateY(-10vh); opacity: 1; }
        100% { transform: translateY(110vh); opacity: 0; }
    }
</style>
</head>
<body>
<div class="card">
    <h1>Happy Valentine’s Day ❤️</h1>
    <h2>Dear <span style="color:#ff4d6d;">Aanya</span> 🌸</h2>
    <p>With all my heart 💕</p>
    <p><strong>Will you be my Valentine?</strong> 💌</p>
    <div class="buttons">
        <button id="yesBtn" onclick="yesClicked()">Yes 💖</button>
        <button id="noBtn">No 😜</button>
    </div>
</div>
<script>
    function yesClicked() {
        alert("Yaaay! 💖🥰 You just made my Valentine perfect! 🌹💌");
    }
    const noBtn = document.getElementById("noBtn");
    noBtn.addEventListener("mouseenter", () => {
        const moveX = Math.random() * 120 - 60; // left/right
        const moveY = Math.random() * 80 - 40;  // up/down
        noBtn.style.transform = `translate(${moveX}px, ${moveY}px)`;
    });
    // Falling hearts
    setInterval(() => {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = Math.random() * 20 + 15 + "px";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 4000);
    }, 300);
</script>
</body>
</html>
