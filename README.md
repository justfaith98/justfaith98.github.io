<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Faith Olajide | Cybersecurity Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 2rem;
      font-family: 'Fira Code', monospace;
      background-color: #0d0d0d; /* Dark background outside the terminal */
      color: #ffffff;
      display: flex;
      justify-content: center;
    }

    .terminal {
      background-color: #e6ccff; /* Lavender terminal box */
      color: #1a1a1a;
      padding: 2rem;
      border-radius: 8px;
      max-width: 800px;
      width: 100%;
      box-shadow: 0 0 15px rgba(204, 153, 255, 0.3);
    }

    .line {
      margin-bottom: 1rem;
    }

    .prompt {
      color: #9900cc;
    }

    .command {
      color: #663399;
    }

    .output {
      color: #333333;
    }

    a {
      color: #4b0082;
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <div class="terminal">
    <div class="line"><span class="prompt">faith@cyber:~$</span> <span class="command">whoami</span></div>
    <div class="line output">Faith Olajide — Cybersecurity Specialist</div>

    <div class="line"><span class="prompt">faith@cyber:~$</span> <span class="command">cat about_me.txt</span></div>
    <div class="line output">Recent Cybersecurity graduate | IT Support Specialist | Passionate about digital defense</div>

    <div class="line"><span class="prompt">faith@cyber:~$</span> <span class="command">ls projects/</span></div>
    <div class="line output">
      phishing-awareness-vm<br>
      sql-injection-lab<br>
      network-traffic-analysis
    </div>

    <div class="line"><span class="prompt">faith@cyber:~$</span> <span class="command">open resume.pdf</span></div>
    <div class="line output"><a href="your-resume.pdf" target="_blank">📄 View My Resume</a></div>

    <div class="line"><span class="prompt">faith@cyber:~$</span> <span class="command">contact --me</span></div>
    <div class="line output">
      Email: faitholajide1@gmail.com<br>
      LinkedIn: <a href="https://linkedin.com/in/faith-olajide-58075514b" target="_blank">linkedin.com/in/faith-olajide</a>
    </div>
  </div>
</body>
</html>
