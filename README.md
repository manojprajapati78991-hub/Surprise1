<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Roshni ❤️</title>

<style>
body {
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff9a9e, #fecfef);
    font-family: Arial, sans-serif;
    overflow: hidden;
}

.container {
    text-align: center;
    position: relative;
    z-index: 2;
}

.question {
    font-size: 2.5rem;
    margin-bottom: 20px;
}

.black-text {
    color: black;
    margin-bottom: 15px;
}

.heart-name {
    display: inline-block;
    color: white;
    background: red;
    padding: 12px 30px;
    border-radius: 50px;
    font-weight: bold;
    font-size: 2rem;
}

.prompt {
    font-size: 1.5rem;
    color: #fff;
    margin-bottom: 20px;
    height: 30px;
}

.buttons {
    position: relative;
    height: 300px;
}

button {
    padding: 15px 30px;
    font-size: 1.2rem;
    border: none;
    border-radius: 40px;
    cursor: pointer;
    position: absolute;
    transition: all 0.3s ease;
}

#yesBtn {
    background-color: #ff2e63;
    color: white;
    left: 35%;
}

#noBtn {
    background-color: #333;
    color: white;
    left: 60%;
}

.message {
    font-size: 1.8rem;
    color: white;
    display: none;
    margin-top: 20px;
}

/* Big I LOVE YOU pop animation */
.love-popup {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.1);
    font-size: 4rem;
    font-weight: bold;
    color: #fff;
    text-shadow: 0 0 20px red, 0 0 40px pink;
    opacity: 0;
    z-index: 999;
    transition: all 1s ease;
}

.love-popup.show {
    transform: translate(-50%, -50%) scale(1.2);
    opacity: 1;
}

/* Floating hearts */
.heart {
    position: absolute;
    bottom: -20px;
    animation: floatUp 4s linear forwards;
    color: red;
}

@keyframes floatUp {
    0% {
        transform: translateY(0) scale(1);
        opacity: 1;
    }
    100% {
        transform: translateY(-800px) scale(2);
        opacity: 0;
    }
}
</style>
</head>

<body>

<!-- 🎵 Replace VIDEO_ID with Ramo Re YouTube ID -->
<iframe width="0" height="0"
src="https://www.youtube.com/embed/VIDEO_ID?autoplay=1&loop=1&playlist=VIDEO_ID"
frameborder="0"
allow="autoplay">
</iframe>

<div class="container">
    <div class="question">
        <div class="black-text">Will you be my valentine?</div>
        <div class="heart-name">❤️ Roshni ❤️</div>
    </div>

    <div class="prompt" id="promptText"></div>

    <div class="buttons">
        <button id="yesBtn">Yes 💖</button>
        <button id="noBtn">No 🙈</button>
    </div>

    <div class="message" id="loveMessage">
        You have made me the happiest person Bakudi ❤️
    </div>
</div>

<!-- BIG POPUP -->
<div class="love-popup" id="lovePopup">
    I LOVE YOU ❤️
</div>

<script>
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const message = document.getElementById("loveMessage");
const promptText = document.getElementById("promptText");
const lovePopup = document.getElementById("lovePopup");

let yesScale = 1;
let noScale = 1;
let noClickCount = 0;
const maxNoClicks = 10;

// NO button logic
noBtn.addEventListener("click", function () {

    noClickCount++;

    if (noClickCount === 2) {
        promptText.innerText = "Please 🥺";
    }

    if (noClickCount === 5) {
        promptText.innerText = "Are you sure? 😢";
    }

    yesScale += 0.15;
    yesBtn.style.transform = "scale(" + yesScale + ")";

    if (noScale > 0.3) {
        noScale -= 0.07;
        noBtn.style.transform = "scale(" + noScale + ")";
    }

    const maxX = window.innerWidth - 100;
    const maxY = window.innerHeight - 100;

    noBtn.style.left = Math.random() * maxX + "px";
    noBtn.style.top = Math.random() * maxY + "px";

    if (noClickCount === maxNoClicks) {
        setTimeout(() => {
            noBtn.style.display = "none";
        }, 300);
    }
});

// YES button click
yesBtn.addEventListener("click", function() {
    document.querySelector(".buttons").style.display = "none";
    promptText.style.display = "none";
    message.style.display = "block";
    startHearts();

    // After 2 seconds show I LOVE YOU popup
    setTimeout(() => {
        lovePopup.classList.add("show");
    }, 2000);
});

// Floating hearts
function startHearts() {
    setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.fontSize = (20 + Math.random() * 30) + "px";
        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 4000);
    }, 200);
}
</script>

</body>
</html>
