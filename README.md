<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy 15th Birthday Navya 🎉</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
:root{
  --pink:#ff4d8d;
  --glass:rgba(255,255,255,.15);
  --blur:blur(18px);
}

*{margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif;}

body{
  background:radial-gradient(circle at top,#ff7eb3,#ff4d8d);
  overflow:hidden;
  color:#fff;
}

/* LOADER */
#loader{
  position:fixed;
  inset:0;
  background:#ff4d8d;
  display:flex;
  align-items:center;
  justify-content:center;
  z-index:999;
}
.loader-heart{
  width:60px;height:60px;
  background:white;
  transform:rotate(45deg);
  animation:pulse 1s infinite;
}
.loader-heart::before,
.loader-heart::after{
  content:'';
  position:absolute;
  width:60px;height:60px;
  background:white;
  border-radius:50%;
}
.loader-heart::before{top:-30px;}
.loader-heart::after{left:-30px;}
@keyframes pulse{
  0%{transform:rotate(45deg) scale(1)}
  50%{transform:rotate(45deg) scale(1.3)}
  100%{transform:rotate(45deg) scale(1)}
}

/* SLIDES */
.slide{
  position:absolute;
  inset:0;
  display:flex;
  align-items:center;
  justify-content:center;
  flex-direction:column;
  text-align:center;
  padding:40px;
  opacity:0;
  transform:scale(1.1);
  transition:1.2s;
}
.slide.active{
  opacity:1;
  transform:scale(1);
}

/* GLASS CARD */
.card{
  background:var(--glass);
  backdrop-filter:var(--blur);
  border-radius:30px;
  padding:50px;
  box-shadow:0 30px 80px rgba(0,0,0,.25);
  max-width:900px;
}

/* TEXT */
h1{
  font-size:3.2rem;
  margin-bottom:20px;
  animation:fadeUp 1.5s;
}
p{
  font-size:1.3rem;
  line-height:1.8;
  animation:fadeUp 2s;
}
@keyframes fadeUp{
  from{opacity:0;transform:translateY(40px)}
  to{opacity:1;transform:translateY(0)}
}

/* BUTTON */
button{
  margin-top:35px;
  padding:16px 40px;
  font-size:1.1rem;
  border:none;
  border-radius:50px;
  background:white;
  color:#ff4d8d;
  cursor:pointer;
  box-shadow:0 15px 40px rgba(0,0,0,.25);
  transition:.3s;
}
button:hover{transform:scale(1.1)}

/* CAKE */
.cake{position:relative;width:260px;height:200px;margin:auto}
.layer{height:65px;width:260px;border-radius:20px;position:absolute}
.l1{bottom:0;background:#ff4d8d}
.l2{bottom:60px;background:#ff7eb3}
.l3{bottom:120px;background:#ffd1e6}
.candle{
  width:14px;height:45px;background:white;
  position:absolute;top:-40px;left:50%;transform:translateX(-50%);
}
.flame{
  width:20px;height:20px;background:gold;
  border-radius:50%;
  position:absolute;top:-18px;left:50%;
  transform:translateX(-50%);
  box-shadow:0 0 25px gold;
  animation:flicker .5s infinite alternate;
}
@keyframes flicker{
  from{transform:translateX(-50%) scale(1)}
  to{transform:translateX(-50%) scale(1.3)}
}

/* FLOATING HEARTS */
.heart{
  position:absolute;
  width:15px;height:15px;
  background:white;
  transform:rotate(45deg);
  animation:float 8s linear infinite;
}
.heart::before,.heart::after{
  content:'';
  width:15px;height:15px;
  background:white;
  border-radius:50%;
  position:absolute;
}
.heart::before{top:-7px}
.heart::after{left:-7px}
@keyframes float{
  to{transform:translateY(-110vh) rotate(720deg);opacity:0}
}

/* FIREWORKS */
canvas{
  position:fixed;
  inset:0;
  z-index:-1;
}
</style>
</head>

<body>

<div id="loader"><div class="loader-heart"></div></div>
<canvas id="fire"></canvas>

<!-- SLIDE 1 -->
<div class="slide active">
  <div class="card">
    <h1>🎉 Happy 15th Birthday Navya 🎉</h1>
    <p>Today the universe celebrates someone truly special ✨</p>
    <button onclick="next()">Begin Journey 💖</button>
  </div>
</div>

<!-- SLIDE 2 -->
<div class="slide">
  <div class="card">
    <h1>💫 A Message For You</h1>
    <p>
      At 15, you are stepping into a world full of dreams, strength and beauty.  
      Your smile heals hearts, your presence brings peace.  
      Never stop believing in yourself 🌸
    </p>
    <button onclick="next()">Next ✨</button>
  </div>
</div>

<!-- SLIDE 3 -->
<div class="slide">
  <div class="card">
    <h1>🎂 Make a Wish</h1>
    <div class="cake">
      <div class="layer l1"></div>
      <div class="layer l2"></div>
      <div class="layer l3"></div>
      <div class="candle"><div class="flame"></div></div>
    </div>
    <button onclick="next()">Celebrate 🎆</button>
  </div>
</div>

<!-- SLIDE 4 -->
<div class="slide">
  <div class="card">
    <h1>🎇 Happy Birthday Navya 🎇</h1>
    <p>
      May your life shine brighter than these fireworks,  
      may your dreams rise higher than the sky,  
      and may happiness follow you always 💕
    </p>
  </div>
</div>

<audio id="music" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3">
</audio>

<script>
/* LOADER */
setTimeout(()=>document.getElementById("loader").style.display="none",2500);

/* SLIDES */
let i=0;
const slides=document.querySelectorAll(".slide");
function next(){
  slides[i].classList.remove("active");
  i=Math.min(i+1,slides.length-1);
  slides[i].classList.add("active");
  document.getElementById("music").play();
}

/* HEARTS */
setInterval(()=>{
  const h=document.createElement("div");
  h.className="heart";
  h.style.left=Math.random()*100+"vw";
  h.style.bottom="-20px";
  h.style.opacity=Math.random();
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),8000);
},600);

/* FIREWORKS */
const c=document.getElementById("fire"),ctx=c.getContext("2d");
c.width=innerWidth;c.height=innerHeight;
let p=[];
function boom(){
  let x=Math.random()*c.width,y=Math.random()*c.height/2;
  for(let i=0;i<120;i++){
    p.push({
      x,y,
      dx:(Math.random()-0.5)*8,
      dy:(Math.random()-0.5)*8,
      life:100,
      col:`hsl(${Math.random()*360},100%,60%)`
    });
  }
}
function draw(){
  ctx.clearRect(0,0,c.width,c.height);
  p.forEach((a,i)=>{
    a.x+=a.dx;a.y+=a.dy;a.life--;
    ctx.fillStyle=a.col;
    ctx.fillRect(a.x,a.y,3,3);
    if(a.life<=0)p.splice(i,1);
  });
  requestAnimationFrame(draw);
}
setInterval(boom,1200);
draw();
</script>

</body>
</html># Happy-birthday-Navya-
