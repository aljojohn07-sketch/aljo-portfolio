 <!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aljo Premium Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
:root{
--bg:#05050a;
--card:#0d0d16;
--text:#e5e7eb;
--accent:#8b5cf6;
}

*{margin:0;padding:0;box-sizing:border-box;font-family:Poppins,sans-serif}
body{background:var(--bg);color:var(--text);overflow-x:hidden}

#particles{position:fixed;width:100%;height:100%;z-index:-1}

.container{max-width:1100px;margin:auto;padding:20px}

.hero{text-align:center;padding-top:60px}
.hero img{width:130px;height:130px;border-radius:50%;border:3px solid var(--accent);box-shadow:0 0 25px var(--accent)}

h1{font-size:2.5rem}
.typing{color:var(--accent);border-right:2px solid var(--accent);padding-right:5px}

.btn{
padding:12px 22px;
border:none;
border-radius:30px;
margin:10px;
background:linear-gradient(45deg,#7c3aed,#a78bfa);
color:#fff;
cursor:pointer;
box-shadow:0 0 15px #7c3aed,0 0 30px #7c3aed;
transition:0.3s;
}

.btn:hover{transform:scale(1.08);box-shadow:0 0 30px #a78bfa}

.section{margin-top:60px}
h2{color:var(--accent);margin-bottom:15px;text-align:center}

.grid{display:grid;gap:20px}

.card{
background:var(--card);
padding:20px;
border-radius:15px;
box-shadow:0 0 15px rgba(139,92,246,0.2);
text-align:center;
transition:0.3s;
}

.card:hover{transform:translateY(-8px) scale(1.03);box-shadow:0 0 25px var(--accent)}

@media(min-width:768px){.grid{grid-template-columns:repeat(2,1fr)}}
@media(min-width:1024px){.grid{grid-template-columns:repeat(3,1fr)}}

form input,form textarea{
width:100%;
padding:10px;
margin:10px 0;
border:none;
border-radius:8px;
background:#1a1a2e;
color:white;
}

</style>
</head>
<body>

<canvas id="particles"></canvas>

<div class="container"><div class="hero">
<img src="yourphoto.jpg">
<h1>Hey, I am <span class="typing" id="typing"></span></h1>
<p>Cybersecurity Professional</p>
<button class="btn">View Work</button>
<button class="btn">Contact Me</button>
<a href="resume.pdf" download><button class="btn">Download Resume</button></a>
</div><div class="section">
<h2>About Me</h2>
<div class="card">I build secure and scalable systems with strong cybersecurity skills.</div>
</div><div class="section">
<h2>Skills</h2>
<div class="grid">
<div class="card">SIEM</div>
<div class="card">IDS</div>
<div class="card">Firewall</div>
<div class="card">Python</div>
<div class="card">PHP</div>
</div>
</div><div class="section">
<h2>Projects</h2>
<div class="grid">
<div class="card">Dispensary System</div>
<div class="card">Crime Reporting System</div>
</div>
</div><div class="section">
<h2>Contact</h2>
<form onsubmit="sendMail(event)">
<input type="text" placeholder="Your Name" required>
<input type="email" placeholder="Your Email" required>
<textarea placeholder="Message" required></textarea>
<button class="btn">Send Message</button>
</form>
</div></div><script>
// typing effect
const text="Aljo";
let i=0;
function typing(){
 if(i<text.length){
 document.getElementById('typing').innerHTML+=text.charAt(i);
 i++;
 setTimeout(typing,150);
 }
}
typing();
// fake mail
function sendMail(e){
 e.preventDefault();
 alert("Message sent successfully! (Demo)");
}
// particles
const canvas=document.getElementById('particles');
const ctx=canvas.getContext('2d');
canvas.width=window.innerWidth;
canvas.height=window.innerHeight;
let particles=[];
for(let i=0;i<80;i++){
particles.push({x:Math.random()*canvas.width,y:Math.random()*canvas.height,r:1.5,dx:Math.random()-0.5,dy:Math.random()-0.5});
}
function draw(){
ctx.clearRect(0,0,canvas.width,canvas.height);
ctx.fillStyle='#8b5cf6';
particles.forEach(p=>{
ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);ctx.fill();
p.x+=p.dx;p.y+=p.dy;
if(p.x<0||p.x>canvas.width)p.dx*=-1;
if(p.y<0||p.y>canvas.height)p.dy*=-1;
});
requestAnimationFrame(draw);
}
draw();
</script>
</body>
</html>
