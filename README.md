# for meseteo
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Meseteo 💖</title>

<style>
body {
    margin: 0;
    padding: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #ff758c, #ff7eb3, #ffc3a0);
    background-size: 300% 300%;
    animation: gradientMove 8s ease infinite;
    overflow: hidden;
    text-align: center;
    color: white;
}

@keyframes gradientMove {
    0% {background-position: 0% 50%;}
    50% {background-position: 100% 50%;}
    100% {background-position: 0% 50%;}
}

.container {
    margin-top: 12vh;
    padding: 20px;
    animation: fadeIn 2s ease;
}

h1 {
    font-size: 2.5em;
}

.name {
    font-size: 3em;
    font-weight: bold;
    text-shadow: 0 0 20px white;
    animation: glow 2s infinite alternate;
}

@keyframes glow {
    from { text-shadow: 0 0 10px white; }
    to { text-shadow: 0 0 25px #fff, 0 0 40px #ff2e63; }
}

button {
    padding: 15px 30px;
    font-size: 18px;
    border: none;
    border-radius: 40px;
    cursor: pointer;
    margin: 10px;
    transition: all 0.3s ease;
}

#yesBtn {
    background: #ff2e63;
    color: white;
}

#noBtn {
    background: white;
    color: #ff2e63;
}

.heart {
    position: absolute;
    font-size: 18px;
    animation: float 6s linear infinite;
}

@keyframes float {
    0% {transform: translateY(100vh);}
    100% {transform: translateY(-10vh);}
}

@keyframes fadeIn {
    from {opacity: 0;}
    to {opacity: 1;}
}
</style>
</head>

<body>

<div class="container">
    <div class="name">Meseteo 💖</div>
    <p>You didn’t just enter my life…</p>
    <p>You quietly became my favorite part of it.</p>
    <h1>Will you be my Valentine? 🌹</h1>

    <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" width="240" style="border-radius:20px;">

    <br><br>

    <button id="yesBtn">Yes, always 💘</button>
    <button id="noBtn">No 🥺</button>
</div>

<audio autoplay loop>
<source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_0c91f8e54c.mp3?filename=romantic-background-112198.mp3" type="audio/mpeg">
</audio>

<script>
let yesSize = 18;
let noSize = 18;

const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");

noBtn.addEventListener("click", function() {
    yesSize += 10;
    noSize -= 4;

    yesBtn.style.fontSize = yesSize + "px";
    yesBtn.style.padding = (15 + yesSize/3) + "px " + (30 + yesSize/3) + "px";
    noBtn.style.fontSize = noSize + "px";

    noBtn.style.transform = "rotate(" + (Math.random()*20-10) + "deg)";

    if (noSize <= 8) {
        noBtn.style.display = "none";
    }
});

yesBtn.addEventListener("click", function() {
    document.body.innerHTML = `
    <div style="margin-top:25vh; animation:fadeIn 1s ease;">
        <h1 style="font-size:3em;">You just made my world brighter 💖</h1>
        <img src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" width="260" style="border-radius:20px;">
        <p>I promise to choose you, every single day, Meseteo.</p>
    </div>
    `;
});

function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "💞";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 10 + "px";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
}

setInterval(createHeart, 300);
</script>

</body>
</html>
