# for-you<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pesan Rahasia Buat Salsa</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #fbc2eb, #a18cd1);
    background-size: 400% 400%;
    animation: gradientBG 8s ease infinite;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
    overflow: hidden;
}

@keyframes gradientBG {
    0% {background-position: 0% 50%;}
    50% {background-position: 100% 50%;}
    100% {background-position: 0% 50%;}
}

.card {
    background: white;
    padding: 35px;
    border-radius: 25px;
    box-shadow: 0 15px 40px rgba(0,0,0,0.2);
    max-width: 420px;
    animation: fadeIn 1s ease-in-out;
    position: relative;
    z-index: 2;
}

button {
    padding: 10px 20px;
    border: none;
    border-radius: 25px;
    font-size: 14px;
    cursor: pointer;
    margin: 5px;
}

#yesBtn {
    background-color: #ff4d6d;
    color: white;
    animation: pulse 1.5s infinite;
}

@keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.08); }
    100% { transform: scale(1); }
}

#noBtn {
    background-color: #6c5ce7;
    color: white;
    position: absolute;
}

.heart {
    position: fixed;
    top: -10px;
    font-size: 20px;
    animation: fall linear forwards;
    z-index: 1;
}

@keyframes fall {
    to {
        transform: translateY(110vh);
        opacity: 0;
    }
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>
</head>

<body>

<div class="card">
    <h1>🚨 PERHATIAN! Pesan Penting & Agak Berbahaya 🚨</h1>
    <p>
        Hai Salsa 😆<br><br>
        Aku punya pengakuan penting...  
        👉 Aku suka kamu, Salsa. 💖<br><br>
        Mau nggak jadi orang favorit aku? 😌
    </p>

    <div style="margin-top:20px; position:relative;">
        <button id="yesBtn" onclick="jawabYes()">Iya 💖</button>
        <button id="noBtn" onmouseover="kabur()">Tidak 🙈</button>
    </div>
</div>

<script>
function jawabYes() {
    document.querySelector(".card").innerHTML = `
        <h1 style="color:#ff4d6d;">YEEAAAYYY 😆💖</h1>
        <h2>Salsa resmi jadi pacarnya Bemby 😎💖</h2>
        <p>Sekarang aku resmi senyum tiap ketemu kamu 😉</p>
    `;
    startHearts();
}

function kabur() {
    const btn = document.getElementById("noBtn");
    btn.style.top = Math.random() * 200 + "px";
    btn.style.left = Math.random() * 200 + "px";
}

function startHearts() {
    setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = (Math.random() * 20 + 15) + "px";
        heart.style.animationDuration = (Math.random() * 2 + 3) + "s";
        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 5000);
    }, 300);
}
</script>

</body>
</html>
