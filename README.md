<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Faith Olajide | Cybersecurity Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code&display=swap" rel="stylesheet">
  <style>
    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
      background-color: #2c003e; /* Deep lavender */
      font-family: 'Fira Code', monospace;
      color: #ccffcc;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 2rem;
    }

    .terminal {
      width: 100%;
      max-width: 800px;
      background-color: #2c003e;
      border-radius: 8px;
      padding: 1.5rem;
      border: 1px solid #774c9e;
      box-shadow: 0 0 20px #a271b8;
      white-space: pre-wrap;
      position: relative;
    }

    .top-bar {
      display: flex;
      gap: 8px;
      position: absolute;
      top: 0.75rem;
      left: 1rem;
    }

    .dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      display: inline-block;
    }

    .red { background-color: #ff5f56; }
    .yellow { background-color: #ffbd2e; }
    .green { background-color: #27c93f; }

    h1, h2 {
      color: #f0caff;
      border-bottom: 1px solid #774c9e;
      padding-bottom: 0.3rem;
    }

    a {
      color: #aaffee;
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }

    nav {
      margin-top: 1rem;
      margin-bottom: 2rem;
    }

    nav a {
      margin-right: 15px;
      font-weight: bold;
    }

    footer {
      text-align: center;
      margin-top: 2rem;
      color: #aa99ff;
    }
  </style>
</head>
<body>
  <div class="terminal">
    <div class="top-bar">
      <span class="dot red"></span>
      <span class="dot yellow"></span>
      <span class="dot green"></span>
    </div>

    <h1>Faith Olajide</h1>
    <p>Cybersecurity & IT Support Specialist</p>
    <nav>
      <a href="#about">About Me</a>
      <a href="#projects">Projects</a>
      <a href="#resume">Resume</a>
      <a href="#contact">Contact</a>
    </nav>

    <section id="about">
      <h2>About Me</h2>
      <p>B.S. Cybersecurity graduate with 7+ years of IT and security experience. I specialize in threat detection, phishing simulations, and technical support. I’m passionate about user education and emerging cybersecurity tools.</p>
    </section>

    <section id="projects">
      <h2>Featured Projects</h2>
      <ul>
        <li><strong>Phishing Simulation VM</strong> — Created VM-based phishing simulations to train employees on threat recognition.</li>
        <li><strong>Threat Intel Automation</strong> — Used Python to automate daily threat feed parsing and anomaly reporting.</li>
        <li><strong>Incident Response SOPs</strong> — Authored 10+ playbooks to standardize response and reduce incident resolution time.</li>
      </ul>
    </section>

    <section id="resume">
      <h2>Resume</h2>
      <p><a href="your-resume.pdf" target="_blank">Download PDF Resume</a></p>
    </section>

    <section id="contact">
      <h2>Contact</h2>
      <p>Email: faitholajide1@gmail.com</p>
      <p>Phone: (240)-469-0970</p>
      <p><a href="https://www.linkedin.com/in/faith-olajide-58075514b/" target="_blank">LinkedIn</a></p>
    </section>

    <footer>
      <p>© 2025 Faith Olajide</p>
    </footer>
  </div>
</body>
</html>
