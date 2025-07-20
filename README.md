<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>faith@terminal:~$</title>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 2rem;
      background-color: #000;
      color: #00ff00;
      font-family: 'Fira Code', monospace;
      font-size: 1rem;
    }

    .terminal {
      max-width: 800px;
      margin: auto;
      white-space: pre-wrap;
    }

    a {
      color: #00ffff;
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }

    .cursor {
      display: inline-block;
      width: 10px;
      background-color: #00ff00;
      animation: blink 1s infinite;
      vertical-align: bottom;
    }

    @keyframes blink {
      0% { opacity: 1; }
      50% { opacity: 0; }
      100% { opacity: 1; }
    }
  </style>
</head>
<body>
  <div class="terminal">
<pre>
faith@portfolio:~$ whoami
Faith Olajide — Cybersecurity & IT Support Specialist

faith@portfolio:~$ cat about_me.txt
B.S. Cybersecurity graduate with 7+ years of IT and security experience.
Specialized in phishing simulations, user education, and threat detection.
Driven by automation, precision, and user-centered security practices.

faith@portfolio:~$ ls projects
🔹 <a href="https://github.com/justfaith98/SDE-1" target="_blank">Phishing Simulation VM</a>
🔹 <a href="https://github.com/justfaith98/SDE-2" target="_blank">Threat Intel Automation</a>
🔹 Incident Response SOPs (Offline)

faith@portfolio:~$ cat resume_and_pptx.txt
📄 <a href="Faith-Olajide-Resume.pdf" target="_blank">Download Resume (PDF)</a>
📊 <a href="cybersecurity-project.pptx" target="_blank">Download Cybersecurity Presentation (PPTX)</a>

faith@portfolio:~$ cat contact_info.txt
📧 Email: <a href="mailto:faitholajide1@gmail.com">faitholajide1@gmail.com</a>
📞 Phone: (240)-469-0970
🔗 <a href="https://www.linkedin.com/in/faith-olajide-58075514b/" target="_blank">LinkedIn</a>
🔗 <a href="https://github.com/justfaith98" target="_blank">GitHub</a>

faith@portfolio:~$ _
<span class="cursor"></span>
</pre>
  </div>
</body>
</html>
