<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Untuk Asra Savira 🤍</title>

<style>
body{
    margin:0;
    padding:0;
    background:linear-gradient(135deg,#ffb6e6,#ffe6fa);
    font-family:'Segoe UI',cursive;
    text-align:center;
    overflow-x:hidden;
    color:#d63384;
}

.section{
    padding:60px 20px;
    max-width:600px;
    margin:auto;
}

h1{color:#ff2e88;font-size:34px;}
h2{color:#ff2e88;margin-top:30px;}

p{
    line-height:1.8;
    margin:15px 0;
    font-size:16px;
}

.buttons{
    margin-top:40px;
    position:relative;
    height:200px;
}

button{
    padding:12px 25px;
    border-radius:30px;
    font-weight:bold;
    border:none;
    cursor:pointer;
    position:absolute;
    transition:0.2s;
}

#yesBtn{
    background:#ff2e88;
    color:white;
    left:30%;
    font-size:18px;
}

#noBtn{
    background:white;
    color:#ff2e88;
    border:2px solid #ff2e88;
    left:55%;
    font-size:18px;
}

.fullscreen{
    position:fixed;
    inset:0;
    background:white;
    display:none;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    z-index:10;
    padding:20px;
    text-align:center;
}

.countdown{
    font-size:70px;
    color:#ff2e88;
}

.bigText{
    font-size:20px;
    max-width:650px;
    line-height:1.8;
    margin-top:20px;
}

.heart{
    position:fixed;
    top:-10px;
    font-size:20px;
    animation:fall linear infinite;
    z-index:0;
}

@keyframes fall{
    0%{transform:translateY(-10vh);}
    100%{transform:translateY(110vh);}
}

.shake{
    animation:shake 0.3s;
}

@keyframes shake{
    0%{transform:translate(0,0);}
    25%{transform:translate(5px,-5px);}
    50%{transform:translate(-5px,5px);}
    75%{transform:translate(5px,5px);}
    100%{transform:translate(0,0);}
}
</style>
</head>

<body>

<!-- MUSIC -->
<audio id="bgMusic" loop>
<source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_c8c8a73467.mp3?filename=romantic-piano-11086.mp3" type="audio/mpeg">
</audio>

<div class="section">
<h1>Hai Asra Savira 🌸</h1>

<p>
Aku nggak tahu sejak kapan semuanya terasa berbeda.
Tapi setiap kali kamu muncul, entah itu lewat chat kecil,
atau cuma notifikasi singkat,
hari yang tadinya biasa aja langsung terasa lebih hangat.
</p>

<p>
Aku suka cara kamu ketawa.
Aku suka cara kamu jawab sesuatu dengan santai tapi bikin aku mikir.
Aku suka hal-hal kecil tentang kamu yang mungkin orang lain nggak sadar.
</p>

<p>
Kita memang belum punya status.
Belum ada kata resmi.
Tapi kalau perasaan bisa jujur tanpa label,
maka aku nyaman sama kamu.
Dan itu cukup berarti buat aku.
</p>

<p>
Aku nggak mau maksa.
Aku nggak mau buru-buru.
Aku cuma mau kamu tahu…
kalau aku tulus.
</p>

<h2>Jadi… mau nggak kamu jadi Valentine-ku? 💘</h2>

<div class="buttons">
<button id="yesBtn" onclick="forceYes()">YES 🤍</button>
<button id="noBtn" onmouseover="moveNo()">NO 🙈</button>
</div>
</div>

<div class="fullscreen" id="takeover">
<div class="countdown" id="countdown">3</div>
<div class="bigText" id="finalText" style="display:none;">
Mungkin kamu sempat ragu.  
Mungkin kamu mencoba menghindar.  

Tapi beberapa perasaan memang nggak datang dua kali 🤍  

Terima kasih sudah memilih untuk tinggal.  
Aku janji ini bukan sekadar lucu-lucuan atau tren Valentine.  

Kalau kamu kasih aku kesempatan,  
aku bakal jaga kamu dengan cara yang paling dewasa,  
paling tulus,  
dan paling lembut yang aku bisa. 🌷💖
</div>
</div>

<script>
const music=document.getElementById("bgMusic");
document.body.addEventListener("click",()=>{music.play();},{once:true});

let noCount=0;
let yesSize=18;
let noSize=18;

function moveNo(){
const noBtn=document.getElementById("noBtn");
const yesBtn=document.getElementById("yesBtn");

noCount++;
document.body.classList.add("shake");
setTimeout(()=>document.body.classList.remove("shake"),300);

noBtn.style.left=Math.random()*80+"vw";
noBtn.style.top=Math.random()*80+"vh";

yesSize+=6;
yesBtn.style.fontSize=yesSize+"px";

noSize-=2;
if(noSize>8){
noBtn.style.fontSize=noSize+"px";
}

if(noCount>=5){
startTakeover();
}
}

function startTakeover(){
const takeover=document.getElementById("takeover");
const countdown=document.getElementById("countdown");
const finalText=document.getElementById("finalText");

takeover.style.display="flex";

let count=3;
let interval=setInterval(()=>{
count--;
countdown.innerText=count;
if(count===0){
clearInterval(interval);
countdown.style.display="none";
finalText.style.display="block";
confettiBoom();
}
},1000);
}

function forceYes(){
startTakeover();
}

function confettiBoom(){
for(let i=0;i<200;i++){
const heart=document.createElement("div");
heart.classList.add("heart");
heart.innerHTML=["💖","💗","💕","💞","🤍"][Math.floor(Math.random()*5)];
heart.style.left=Math.random()*100+"vw";
heart.style.animationDuration=Math.random()*3+2+"s";
document.body.appendChild(heart);
setTimeout(()=>heart.remove(),5000);
}
}

setInterval(()=>{
const heart=document.createElement("div");
heart.classList.add("heart");
heart.innerHTML="🤍";
heart.style.left=Math.random()*100+"vw";
heart.style.animationDuration=Math.random()*4+3+"s";
document.body.appendChild(heart);
setTimeout(()=>heart.remove(),6000);
},800);
</script>

</body>
</html>
