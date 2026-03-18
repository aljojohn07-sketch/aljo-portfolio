<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aljo Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
:root {
  --bg:#05050a;
  --card:#0d0d16;
  --text:#e5e7eb;
  --accent:#8b5cf6;
}

*{margin:0;padding:0;box-sizing:border-box;font-family:Poppins,sans-serif}
body{background:var(--bg);color:var(--text);overflow:hidden}

/* PARTICLES */
#particles{
 position:fixed;
 width:100%;
 height:100%;
 z-index:-1;
}

header{text-align:center;padding:40px}
header img{width:120px;height:120px;border-radius:50%;border:3px solid var(--accent)}

h1{font-size:2.5rem}
p{opacity:0.8}

.btn{
 padding:12px 25px;
 border:none;
 border-radius:30px;
 background:linear-gradient(45deg,#7c3aed,#a78bfa);
 color:#fff;
 cursor:pointer;
 box-shadow:0 0 15px #7c3aed,0 0 30px #7c3aed;
 transition:0.3s;
}

.btn:hover{
 box-shadow:0 0 25px #a78bfa,0 0 50px #a78bfa;
 transform:scale(1.05);
}

.section{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center}

.slider{display:flex;width:300vw;transition:0.7s}
.slide{width:100vw}

.card{
 background:var(--card);
 padding:20px;
 margin:10px;
 border-radius:12px;
 width:80%;
 text-align:center;
 box-shadow:0 0 15px rgba(139,92,246,0.2);
}

.controls{position:fixed;bottom:20px;left:50%;transform:translateX(-50%);display:flex;gap:10px}
.controls button{border:none;border-radius:50%;padding:10px;background:var(--accent);color:white;cursor:pointer}

</style>
</head>
<body>

<canvas id="particles"></canvas>

<div class="slider" id="slider">

<!-- HERO -->
<div class="slide">
<section class="section">
<header>
<img src="yourphoto.jpg">
<h1>Hey, I am Aljo</h1>
<p>Cybersecurity Professional</p>
<br>
<button class="btn">View My Work</button>
<button class="btn">Get in Touch</button>
<br><br>
<a href="resume.pdf" download><button class="btn">Download Resume</button></a>
</header>
</section>
</div>

<!-- ABOUT -->
<div class="slide">
<section class="section">
<h2>About Me</h2>
<div class="card">I craft secure and efficient digital systems with cybersecurity expertise.</div>
<h2>Skills</h2>
<div class="card">SIEM • IDS • Firewall • Python • PHP</div>
</section>
</div>

<!-- PROJECTS -->
<div class="slide">
<section class="section">
<h2>Projects</h2>
<div class="card">Dispensary Management System</div>
<div class="card">Online Crime Reporting System</div>
<h2>Contact</h2>
<div class="card">aljojohn07@gmail.com</div>
</section>
</div>

</div>

<div class="controls">
<button onclick="move(0)">1</button>
<button onclick="move(1)">2</button>
<button onclick="move(2)">3</button>
</div>

<script>
// SLIDER
function move(i){document.getElementById('slider').style.transform=`translateX(-${i*100}vw)`}

// PARTICLES
const canvas=document.getElementById('particles');
const ctx=canvas.getContext('2d');
canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

let particles=[];
for(let i=0;i<80;i++){
 particles.push({x:Math.random()*canvas.width,y:Math.random()*canvas.height,r:2,dx:Math.random()-0.5,dy:Math.random()-0.5});
}

function draw(){
 ctx.clearRect(0,0,canvas.width,canvas.height);
 ctx.fillStyle='#8b5cf6';
 particles.forEach(p=>{
  ctx.beginPath();
  ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
  ctx.fill();
  p.x+=p.dx;
  p.y+=p.dy;
  if(p.x<0||p.x>canvas.width)p.dx*=-1;
  if(p.y<0||p.y>canvas.height)p.dy*=-1;
 });
 requestAnimationFrame(draw);
}

draw();
</script></body>
</html>
