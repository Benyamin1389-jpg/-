<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>😈 مردم‌آزار | سایت اعصاب‌خردکن</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    font-family:Tahoma,Arial,sans-serif;
    min-height:100vh;
    background:linear-gradient(135deg,#16001f,#31005c,#09001a);
    color:white;
    overflow:hidden;
}

.container{
    width:92%;
    max-width:900px;
    margin:40px auto;
    text-align:center;
}

.logo{
    font-size:42px;
    font-weight:bold;
    margin-bottom:10px;
}

.subtitle{
    color:#d7bfff;
    margin-bottom:30px;
}

.card{
    background:rgba(255,255,255,.08);
    border:1px solid rgba(255,255,255,.15);
    backdrop-filter:blur(15px);
    border-radius:25px;
    padding:35px 20px;
    box-shadow:0 20px 60px rgba(0,0,0,.4);
}

h2{
    margin-bottom:15px;
}

#message{
    min-height:55px;
    color:#ffd6ff;
    font-size:18px;
    margin:15px;
}

.stats{
    display:flex;
    justify-content:center;
    gap:15px;
    flex-wrap:wrap;
    margin:25px 0;
}

.stat{
    background:rgba(255,255,255,.08);
    padding:15px 25px;
    border-radius:15px;
}

button{
    border:none;
    padding:15px 25px;
    border-radius:14px;
    font-size:17px;
    cursor:pointer;
    transition:.2s;
    font-family:inherit;
}

button:hover{
    transform:scale(1.05);
}

#mainBtn{
    background:linear-gradient(135deg,#ff3cac,#784ba0);
    color:white;
    box-shadow:0 8px 30px rgba(255,60,172,.35);
    position:relative;
}

.secondary{
    background:#fff;
    color:#28003f;
    margin:8px;
}

#escapeBtn{
    background:#ff1744;
    color:white;
    position:fixed;
    left:50%;
    top:78%;
    transform:translate(-50%,-50%);
    z-index:10;
}

#escapeBtn:hover{
    transform:translate(-50%,-50%) scale(1.08);
}

#game{
    display:none;
    margin-top:25px;
}

#target{
    width:55px;
    height:55px;
    border-radius:50%;
    background:#ff3cac;
    position:absolute;
    cursor:pointer;
    box-shadow:0 0 25px #ff3cac;
}

footer{
    margin-top:25px;
    color:#a98bc0;
    font-size:13px;
}

#flash{
    position:fixed;
    inset:0;
    background:white;
    opacity:0;
    pointer-events:none;
    transition:.1s;
}

@media(max-width:600px){
    .logo{font-size:32px;}
    .card{padding:25px 12px;}
}
</style>
</head>

<body>

<div id="flash"></div>

<div class="container">

    <div class="logo">😈 مردم‌آزار</div>

    <div class="subtitle">
        جایی که اعصاب شما فقط یک پیشنهاد است!
    </div>

    <div class="card">

        <h2>آماده‌ای؟ 😏</h2>

        <div id="message">
            روی دکمه زیر کلیک کن... اگر جرأت داری!
        </div>

        <button id="mainBtn" onclick="annoy()">
            اینجا کلیک کن
        </button>

        <div class="stats">
            <div class="stat">
                😵 اعصاب:
                <b id="anger">0</b>٪
            </div>

            <div class="stat">
                🖱️ کلیک:
                <b id="clicks">0</b>
            </div>
        </div>

        <button class="secondary" onclick="startGame()">
            🎯 بازی اعصاب‌خردکن
        </button>

        <button class="secondary" onclick="fakeButton()">
            🎁 جایزه من
        </button>

        <div id="game">
            <h3>🎯 توپ را بگیر!</h3>
            <p style="margin:10px">اگر توانستی 😈</p>
            <div id="target" onclick="hitTarget()"></div>
        </div>

    </div>

    <footer>
        ساخته شده برای سرگرمی 😈 | هیچ اطلاعاتی از شما ذخیره نمی‌شود
    </footer>

</div>

<button id="escapeBtn" onclick="escapeClick()">
    خروج از سایت
</button>

<script>

let clicks = 0;
let anger = 0;

const messages = [
    "😂 فکر کردی همین بود؟",
    "نه نه! دوباره امتحان کن.",
    "تقریباً موفق شدی... تقریباً!",
    "😈 خودت خواستی!",
    "دکمه بعدی شاید بهتر باشد...",
    "سیستم در حال بررسی سطح صبر شماست.",
    "🤨 چرا هنوز ادامه میدی؟",
    "یک کلیک دیگر و شاید اتفاقی بیفتد!",
    "تبریک! هیچ اتفاقی نیفتاد 😂",
    "شما رسماً وارد منطقه مردم‌آزاری شدید."
];

function annoy(){

    clicks++;
    anger = Math.min(100, anger + Math.floor(Math.random()*9)+3);

    document.getElementById("clicks").textContent = clicks;
    document.getElementById("anger").textContent = anger;

    let random = Math.floor(Math.random()*messages.length);

    document.getElementById("message").textContent =
        messages[random];

    if(anger >= 80){
        document.getElementById("message").textContent =
        "🔥 سطح اعصاب شما بحرانی شد!";
    }

    if(Math.random() < .25){
        moveMainButton();
    }
}

function moveMainButton(){

    const btn = document.getElementById("mainBtn");

    btn.style.position = "fixed";

    let x = Math.random() * (window.innerWidth - 180);
    let y = Math.random() * (window.innerHeight - 100);

    btn.style.left = x + "px";
    btn.style.top = y + "px";
}

function fakeButton(){

    const messages = [
        "🎁 جایزه شما: هیچ!",
        "تبریک! شما گول خوردید 😂",
        "جایزه در راه است... ولی راهش را پیدا نکرد.",
        "🏆 جایزه ویژه: یک لبخند!"
    ];

    alert(messages[Math.floor(Math.random()*messages.length)]);
}

function escapeClick(){

    const btn = document.getElementById("escapeBtn");

    let x = Math.random() * (window.innerWidth - 160);
    let y = Math.random() * (window.innerHeight - 80);

    btn.style.left = x + "px";
    btn.style.top = y + "px";

    btn.style.transform = "none";

    document.getElementById("message").textContent =
        "😂 فرار کردی؟ دکمه خروج هم از دستت فرار کرد!";
}

function startGame(){

    document.getElementById("game").style.display = "block";

    moveTarget();
}

function moveTarget(){

    const target = document.getElementById("target");

    let maxX = window.innerWidth - 80;
    let maxY = window.innerHeight - 100;

    target.style.left =
        Math.random()*maxX + "px";

    target.style.top =
        Math.random()*maxY + "px";
}

function hitTarget(){

    clicks++;
    anger += 5;

    if(anger > 100) anger = 100;

    document.getElementById("clicks").textContent = clicks;
    document.getElementById("anger").textContent = anger;

    document.getElementById("message").textContent =
        "😳 گرفتی! ولی دوباره فرار کرد...";

    moveTarget();
}

document.addEventListener("keydown",function(e){

    if(e.key === "Escape"){

        document.getElementById("message").textContent =
        "😂 دکمه Escape هم جواب نداد!";
    }

});

</script>

</body>
</html>
