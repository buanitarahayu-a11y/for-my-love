<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">

<style>
body{
margin:0;
display:flex;
justify-content:flex-start;
align-items:center;
height:100vh;
background:#111;
color:#fff;
font-family:Arial,sans-serif;
font-size:25px;
font-weight:bold;
cursor:pointer;
overflow:hidden;
padding:30px;
box-sizing:border-box;
}

#text{
width:60%;
text-align:left;
line-height:1.6;
z-index:2;
}

#text::after{
content:"|";
animation:blink .8s infinite;
}

@keyframes blink{
50%{
opacity:0;
}
}

.heart{
position:fixed;
top:-20px;
font-size:10px;
pointer-events:none;
animation:fall linear forwards;
z-index:1;
}

@keyframes fall{
to{
transform:translateY(110vh) rotate(360deg);
opacity:0;
}
}

audio{
position:fixed;
bottom:20px;
left:30px;
z-index:3;
}
</style>
</head>

<body>

<div id="text"></div>

<audio controls loop>
<source src="my lovely boiprenn.mp3" type="audio/mpeg">
Browser kamu tidak mendukung audio.
</audio>

<script>
const text=document.getElementById("text");

const words="KLIKK DULUU SAYANGGKUUU HEWHEHWHEHHWE APAA YAAA LET MI THINKK APAA YAAA AKU LUPA MAU NGETIK APAAN HEHWEHWHE HMMZZZ JADII GINIII dear weasley, you have the most handsome face in the world. i love the way you smile and your gentle demeanor. i love how you always do your best. if i could spend every minute of my life supporting you then i would die happy. the fact that you're alive brings me so much joy and i'm honored to be on the same planet as you. i love you so much it hurts. WICII, I JUST LOVEEEE YOU SOO MUCHHHH MY LOVEEE ♥♥♥♥";

let i=0;

function type(){
if(i<words.length){
text.textContent+=words.charAt(i);
i++;
setTimeout(type,130);
}
}

type();

function createHeart(){
const heart=document.createElement("div");
heart.classList.add("heart");
heart.innerHTML="❤";

heart.style.color="red";
heart.style.left=Math.random()*window.innerWidth+"px";
heart.style.fontSize=(15+Math.random()*25)+"px";
heart.style.animationDuration=(3+Math.random()*3)+"s";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},6000);
}

function createFlower(){
const flower=document.createElement("div");
flower.classList.add("heart");
flower.innerHTML="🌼";

flower.style.left=Math.random()*window.innerWidth+"px";
flower.style.fontSize=(18+Math.random()*22)+"px";
flower.style.animationDuration=(4+Math.random()*3)+"s";

document.body.appendChild(flower);

setTimeout(()=>{
flower.remove();
},7000);
}

setInterval(createHeart,250);
setInterval(createFlower,350);
</script>

</body>
</html>
