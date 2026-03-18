<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Aljo Aji John | Portfolio</title> 
  
  <!-- Google Font --> 
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">  
 
  <style>
    :root {
      --bg: #0f172a;
      --card: #020617;
      --text: #e2e8f0;
      --accent: #38bdf8;
    }

    body.light {
      --bg: #f8fafc;
      --card: #ffffff;
      --text: #0f172a;
      --accent: #0284c7;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: var(--bg);
      color: var(--text);
      transition: 0.3s;
    }

    header {
      text-align: center;
      padding: 40px 20px;
    }

    header img {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      border: 3px solid var(--accent);
      margin-bottom: 15px;
    }

    header h1 {
      font-size: 2.5rem;
    }

    header p {
      opacity: 0.8;
    }

    nav {
      display: flex;
      justify-content: center;
      gap: 20px;
      padding: 10px;
    }

    nav a {
      text-decoration: none;
      color: var(--accent);
      font-weight: 600;
    }

    .toggle {
      position: fixed;
      top: 15px;
      right: 15px;
      cursor: pointer;
      padding: 10px;
      background: var(--card);
      border-radius: 10px;
    }

    section {
      max-width: 900px;
      margin: auto;
      padding: 40px 20px;
    }

    h2 {
      color: var(--accent);
      margin-bottom: 15px;
    }

    .card {
      background: var(--card);
      padding: 20px;
      margin: 15px 0;
      border-radius: 12px;
      opacity: 0;
      transform: translateY(30px);
      transition: 0.6s ease;
    }

    .card.show {
      opacity: 1;
      transform: translateY(0);
    }

    button {
      padding: 10px 15px;
      background: var(--accent);
      border: none;
      border-radius: 6px;
      cursor: pointer;
      margin-top: 10px;
    }

    footer {
      text-align: center;
      padding: 20px;
      opacity: 0.7;
    }
  </style></head>
<body><div class="toggle" onclick="toggleMode()">🌙</div><header>
  <img src="https://via.placeholder.com/120" alt="Profile Photo" />
  <h1>Aljo Aji John</h1>
  <p>Cybersecurity Professional | MCA Student</p>
  <a href="resume.pdf" download>
    <button>Download Resume</button>
  </a>
</header><nav>
  <a href="#about">About</a>
  <a href="#skills">Skills</a>
  <a href="#projects">Projects</a>
  <a href="#contact">Contact</a>
</nav><section id="about">
  <h2>About Me</h2>
  <div class="card">
    <p>Aspiring cybersecurity professional skilled in SOC operations, threat analysis, and development.</p>
  </div>
</section><section id="skills">
  <h2>Skills</h2>
  <div class="card">
    <h3>Cybersecurity</h3>
    <p>Threat Analysis, SIEM, IDS, Firewall Management</p>
  </div>
  <div class="card">
    <h3>Development</h3>
    <p>Python (Django), PHP, MySQL</p>
  </div>
</section><section id="projects">
  <h2>Projects</h2>
  <div class="card">
    <h3>Dispensary Management System</h3>
    <p>Django-based system for medical management.</p>
  </div>
  <div class="card">
    <h3>Online Crime Reporting System</h3>
    <p>Web platform for Kerala Police reporting.</p>
  </div>
</section><section id="contact">
  <h2>Contact</h2>
  <div class="card">
    <p>Email: aljojohn07@gmail.com</p>
    <p>Phone: +91 6282592727</p>
    <button onclick="alert('Contact me via email!')">Hire Me</button>
  </div>
</section><footer>
  <p>© 2026 Aljo Aji John</p>
</footer><script>
  function toggleMode() {
    document.body.classList.toggle('light');
  }

  const cards = document.querySelectorAll('.card');

  window.addEventListener('scroll', () => {
    cards.forEach(card => {
      const top = card.getBoundingClientRect().top;
      if (top < window.innerHeight - 50) {
        card.classList.add('show');
      }
    });
  });
</script></body>
</html>
