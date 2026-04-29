<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Andualem | Frontend Developer</title>

<!-- Google Font -->
<link href="https://fonts.googleapis.com/css2?family=Poppins&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Poppins',sans-serif;scroll-behavior:smooth;transition:.3s}

/* DARK MODE */
.dark{background:#111;color:#fff}

/* NAV */
header{
position:fixed;width:100%;top:0;background:#111;color:#fff;padding:15px;z-index:1000;
}
nav{display:flex;justify-content:space-between;align-items:center}
nav ul{display:flex;gap:20px;list-style:none}
nav a{color:#fff;text-decoration:none}
nav a:hover{color:orange}

/* HERO */
.hero{
height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;
background:linear-gradient(rgba(0,0,0,.6),rgba(0,0,0,.6)),url('https://picsum.photos/1600/900');
color:#fff;text-align:center;
}

/* BUTTON */
button{
padding:10px 20px;border:none;background:orange;color:#fff;border-radius:20px;
cursor:pointer;margin-top:10px;transition:.3s;
}
button:hover{background:#ff6600;transform:scale(1.05)}

/* SECTION */
section{padding:80px 20px;text-align:center}

/* GRID */
.projects{
display:grid;grid-template-columns:repeat(2,1fr);gap:20px;
}
.project{
background:#f4f4f4;border-radius:10px;overflow:hidden;cursor:pointer;transition:.3s;
}
.project img{width:100%;height:180px;object-fit:cover}
.project:hover{transform:scale(1.05);box-shadow:0 10px 25px rgba(0,0,0,.4)}

/* SKILLS */
.skills span{
display:inline-block;margin:10px;padding:10px 15px;background:orange;color:#fff;border-radius:20px;
}

/* FORM */
form{
display:flex;flex-direction:column;gap:10px;max-width:400px;margin:auto;
}
input,textarea{padding:10px}

/* FOOTER */
footer{background:#111;color:#fff;padding:20px}

/* ANIMATION */
.fade{opacity:0;transform:translateY(20px);transition:1s}
.show{opacity:1;transform:translateY(0)}

@media(max-width:768px){
.projects{grid-template-columns:1fr}
}
</style>
</head>

<body>

<header>
<nav>
<h2>Andualem 😎</h2>
<ul>
<li><a href="#home">Home</a></li>
<li><a href="#about">About</a></li>
<li><a href="#skills">Skills</a></li>
<li><a href="#projects">Projects</a></li>
<li><a href="#contact">Contact</a></li>
</ul>
<button onclick="toggleDark()">🌙</button>
</nav>
</header>

<!-- HERO -->
<section class="hero fade" id="home">
<h1>Hello, I'm Andualem</h1>
<p>Frontend Developer</p>
<button onclick="scrollToSection('projects')">View My Work</button>
</section>

<!-- ABOUT -->
<section id="about" class="fade">
<h2>About Me</h2>
<p>I am a passionate frontend developer who builds modern and responsive websites.</p>
</section>

<!-- SKILLS -->
<section id="skills" class="fade">
<h2>Skills</h2>
<div class="skills">
<span>HTML</span>
<span>CSS</span>
<span>JavaScript</span>
</div>
</section>

<!-- PROJECTS -->
<section id="projects" class="fade">
<h2>Projects 🚀</h2>
<div class="projects">

<div class="project">
<img src="https://picsum.photos/400?1">
<h3>Portfolio Website</h3>
<button>Live</button>
<button>Code</button>
</div>

<div class="project">
<img src="https://picsum.photos/400?2">
<h3>Calculator App</h3>
<button>Live</button>
<button>Code</button>
</div>

</div>
</section>

<!-- CONTACT -->
<section id="contact" class="fade">
<h2>Contact</h2>
<form onsubmit="sendMessage(event)">
<input placeholder="Name" required>
<input placeholder="Email" required>
<textarea placeholder="Message" required></textarea>
<button>Send</button>
</form>
</section>

<footer>
<p>© 2026 Andualem</p>
</footer>

<script>
// DARK MODE
function toggleDark(){
document.body.classList.toggle("dark");
}

// SCROLL
function scrollToSection(id){
document.getElementById(id).scrollIntoView();
}

// FORM
function sendMessage(e){
e.preventDefault();
alert("Message sent!");
}

// ANIMATION
const fades=document.querySelectorAll(".fade");
window.addEventListener("scroll",()=>{
fades.forEach(el=>{
if(el.getBoundingClientRect().top < window.innerHeight-100){
el.classList.add("show");
}
});
});
</script>

</body>
</html>
