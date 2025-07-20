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
      background-color: #2c003e;
      font-family: 'Fira Code', monospace;
      color: #ccffcc;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 2rem;
    }

    .terminal {
      width: 100%;
      max-width: 850px;
      background-color: #2c003e;
      border-radius: 8px;
      padding: 2rem;
      box-shadow: 0 0 20px #aa88cc;
      position: relative;
    }

    .top-bar {
      display: flex;
      gap: 8px;
      position: absolute;
      top: 1rem;
      left: 1.5rem;
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

    .content {
      margin-top: 2.5rem;
      white-space: pre-wrap;
      line-height: 1.6;
    }

    .prompt {
      color: #ccffcc;
    }

    .command {
      color: #aaffee;
    }

    .output {
      color: #f0caff;
    }

    .cursor {
      display: inline-block;
      width: 10px;
      height: 20px;
      background-color: #ccffcc;
      animation: blink 1s step-end infinite;
    }

    @keyframes blink {
      from, to { background: transparent; }
      50% { background: #ccffcc; }
    }

    a {
      color: #99e6ff;
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
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

    <div class="content" id="terminal-content">
      <div class="prompt">faith@cyber:~$ <span class="command">whoami</span></div>
      <div class="output">Faith Olajide - Cybersecurity Specialist</div>

      <div class="prompt">faith@cyber:~$ <span class="command">cat about_me.txt</span></div>
      <div class="output">
        BS in Cybersecurity | IT Support Specialist | Security Awareness Advocate
        Skilled in phishing simulation, threat detection, and incident response.
      </div>

      <div class="prompt">faith@cyber:~$ <span class="command">ls projects/</span></div>
      <div class="output">
        phishing-vm-employee-training/  
        automated-threat-intel/  
        incident-response-playbooks/
      </div>

      <div class="prompt">faith@cyber:~$ <span class="command">open resume.pdf</span></div>
      <div class="output"><a href="your-resume.pdf" target="_blank">📄 View My Resume</a></div>

      <div class="prompt">faith@cyber:~$ <span class="command">contact --me</span></div>
      <div class="output">
        Email: faitholajide1@gmail.com  
        LinkedIn: <a href="https://linkedin.com/in/faith-olajide-58075514b" target="_blank">linkedin.com/in/faith-olajide</a>
      </div>

      <div class="prompt">faith@cyber:~$ <span class="cursor"></span></div>
    </div>
  </div>
</body>
</html>
