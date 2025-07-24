_config.yml
title: Your Name's Portfolio # Replace with your name
description: Cybersecurity Student | Aspiring Security Engineer # Replace with your professional title/description
show_downloads: false
google_analytics:
theme: jekyll-theme-hacker

# Navigation links (optional)
nav_links:
  - name: Home
    url: /
  - name: Resume
    url: /resume.html
  - name: Labs
    url: /labs.html
  - name: Senior Design Project
    url: /senior-design.html

# Social links (optional)
github_username: justfaith98 # Replace with your GitHub username
linkedin_username: faith-olajide-58075514b # Replace with your LinkedIn username
email: your-email@example.com # Replace with your email


index.md
---
layout: default
title: Home
---

# Welcome to My Portfolio!

Hello! I'm excited to showcase my work and experiences in cybersecurity and IT. This page serves as a central hub for my resume, academic labs, and my senior design project.

Feel free to explore the different sections to learn more about my skills, projects, and what I've been working on.

* [**My Resume**](/resume.html): A detailed overview of my education, experience, and skills.
* [**Completed Labs**](/labs.html): Highlights from my hands-on lab assignments in scripting, UNIX/Linux, and networking.
* [**Senior Design Project**](/senior-design.html): An in-depth look at my project on using Virtual Machines for workplace phishing attack mitigation.

Thanks for visiting!


resume.md
---
layout: default
title: Resume
---

# My Resume

## Faith Olajide
**Email:** faitholajide1@gmail.com | **Phone:** (240)-469-0970 | **LinkedIn:** [linkedin.com/in/faith-olajide-58075514b](https://linkedin.com/in/faith-olajide-58075514b) | **GitHub Page:** [https://justfaith98.github.io](https://justfaith98.github.io)

---

### Summary

Proficient cybersecurity and help desk technician with 7+ years of experience identifying and mitigating risks across enterprise networks, systems, and applications. Skilled in security policy implementation, threat detection, system hardening, and end-user support. Adept at resolving technical issues and aligning IT solutions with best security practices. Strong communicator and collaborative team player passionate about digital protection and user empowerment.

---

### Education

**Capitol Technology University**, Laurel, MD
*Bachelor of Applied Science in Cybersecurity* - Graduated 2024 (Jan 2020 – April 2024)
*Google Cybersecurity Certification* - March 2025
*Cybersecurity Asset Manager* - March 2025

---

### Technical Skills

* **Security Tools:** Splunk, CrowdStrike, Microsoft Defender, Mimecast, KnowBe4, Zscaler, Magnet AXIOM
* **Incident Response & Threat Intelligence:** SIEM monitoring, IDS/IPS systems, MITRE ATT&CK
* **Network & System Administration:** Active Directory, Exchange, Multi-Factor Authentication, TCP/IP
* **Languages & Platforms:** Python, C, C++, SQL, Azure, AWS, Google Cloud, HTML/CSS
* **Tools:** Kali Linux, Metasploit, BurpSuite, Wireshark, Nmap, FTK, EnCase

---

### Cybersecurity Projects & Achievements

**CS230 Final Project: Hash Table Implementation**
* Implemented a C++ hash table to manage client information (ID, name, balance).
* Developed functionalities for adding, editing, finding, viewing, and removing records.
* Utilized a linked list for collision resolution within the hash table.

**Incident Response Process Development**
* Investigated and escalated 25+ anomalies weekly using firewall and system logs; automated triage processes using Python, improving response time by 35%.
**Operations Documentation**
* Developed 10+ standardized playbooks and SOPs for incident handling and system configuration, improving team onboarding speed by 50%.
**Threat Intelligence & Risk Mitigation**
* Analyzed threat feeds daily and coordinated patching efforts with a 100% closure rate on critical vulnerabilities within 72 hours.

---

### Technical Experience

**Capitol Technology University** | May 2022 – Aug 2024
*IT Help Desk Technician*
* Resolved 100+ monthly tickets in ConnectWise with 98% SLA.
* Managed 200+ AD accounts, MFA setups, and workstation upgrades.
* Led campus-wide upgrade of 150+ workstations with full device encryption and AV compliance.
* Wrote SOPs used by interns and staff for secure device configuration.

**Capitol Technology University** | April 2020 – May 2022
*Cybersecurity Technician*
* Monitored firewall logs for 500+ endpoints, escalating 20+ verified threats monthly to the SOC team.
* Used Python to automate daily report generation, reducing manual workload by 40%.
* Coordinated vulnerability patch cycles, increasing monthly compliance from 65% to 90%.
* Maintained 30+ documented SOPs covering incident response and device hardening.

**Staples** | Mar 2018 – Apr 2020
*Service Desk Tier 1*
* Resolved 75+ weekly support issues across 14 client networks, including POS, desktops, and VPN.
* Diagnosed and fixed endpoint issues remotely, reducing escalation tickets by 20%.
* Supported AD user provisioning and laptop configuration aligned with secure access policies.
* Assisted in POS upgrades and Wi-Fi deployments aboard 3 enterprise cruise clients.

**University Program** | Aug 2023 – Dec 2023
*Cybersecurity Lab Mentor (TA)*
* Led hands-on lab sessions for 40+ students across courses in digital forensics, secure coding, and intrusion detection.
* Guided students through tools such as Kali Linux, Wireshark, and FTK for simulated threat scenarios.
* Collaborated with faculty to refine and update 5+ lab manuals and SOPs to align with NIST/NICE standards.
* Mentored 10+ undergraduates through secure coding practices using C++ and object-oriented programming.

---

### Volunteer & Activities

* **Volunteer:** GenCyber Assistant, Cybersecurity Peer Mentor, Creative Juices (Art Club) President (2023-2024)
* **Conferences:** Capitol Technology HammerCon
* **Hackathons:** Capitol Tech CTF (2023)

---

### Work Authorization

* U.S. Citizen
* Open to Relocation

labs.md
---
layout: default
title: Labs
---

# Completed Labs

Here are some of the key lab assignments I have completed, demonstrating my practical skills in various areas of IT and cybersecurity.

---

## CT-206 Scripting Languages: Project 1 - Flux Capacitor Temperature Monitor

This project involved developing a Python script to monitor the fictional "Flux Capacitor's" temperature and provide operational status notifications.

**Key Learnings:**
* **Python Fundamentals:** Input/output operations, conditional statements (`if-elif-else`), data type conversion (string to float).
* **Scripting Logic:** Implementing decision-making based on temperature ranges to determine operational status (too hot, normal, too cold).
* **Problem Solving:** Translating real-world (albeit fictional) requirements into executable code.

**Script Requirements:**
* Take temperature input from the keyboard.
* Display the entered temperature and a corresponding message:
    * Above 88.9 degrees: "too hot and needs to be shutoff"
    * Between 88.8 and 60.2 degrees: "running in normal status"
    * Anything else: "running too cold and the system maybe off, please check to make sure it is on"

---

## CT-152 UNIX/Linux Crash Course

This lab provided hands-on experience with fundamental UNIX/Linux commands and concepts, crucial for system administration and cybersecurity.

**Key Learnings:**
* **Basic Navigation:** `cd`, `ls`, `pwd` for moving around the file system and listing directory contents.
* **File Operations:** Creating and editing files with `nano`.
* **Help and Manuals:** Using the `man` command to understand command-line utilities.
* **System Information:** Checking date/time (`date`, `cal`), identifying the current shell (`echo $SHELL`), and listing running processes (`ps x`).
* **Command Piping:** Chaining commands together using `|` (e.g., `cat | less`).
* **User Management:** Identifying other users on the system (`who`).
* **History Management:** Saving command history to a file (`history > fileForHistory.txt`).
* **Archiving:** Creating tar archives (`tar -zcvf`).
* **File Transfer:** Downloading files using FTP/SFTP.
* **Scripting Execution:** Invoking Perl and Python scripts from the shell.
* **Text Processing:** Demonstrations of `grep`, `sed`, and `awk` for searching, substituting, and processing text.
* **Package Management:** Basic understanding of `apt` for installing software packages.

---

## Packet Tracer - Network Representation

This assignment focused on identifying and understanding common network components and topologies using Cisco Packet Tracer.

**Key Learnings:**
* **Network Device Identification:** Differentiating between end devices (e.g., PCs, laptops), intermediary devices (e.g., routers, switches), and media connections.
* **Network Topologies:** Understanding the representation of LANs (Local Area Networks) and WANs (Wide Area Networks).
* **Client-Server Model:** Basic explanation of how clients and servers interact in a network.
* **Intermediary Device Functions:** Understanding their role in interconnecting devices and connecting hosts to networks.
* **Network Media Criteria:** Factors influencing the choice of network media (e.g., distance, speed).
* **Internet Concepts:** A simplified view of the internet's structure and common connection methods for home users and businesses.


senior-design.md
---
layout: default
title: Senior Design Project
---

# Senior Design Project: Using Virtual Machines for Workplace Phishing Attack Mitigation

My senior design project focused on developing a comprehensive, hands-on training module to combat the rising threat of phishing attacks in the workplace. The core of this project involved leveraging virtual machines (VMs) to simulate realistic phishing scenarios, providing employees with a safe and controlled environment to learn how to identify, prevent, and mitigate these cyber threats.

---

## Project Background and Problem Statement

Phishing attacks continue to be a primary source of monetary loss and data breaches for companies, despite advancements in cybersecurity awareness. Traditional training methods often fall short in adequately preparing employees. My project aimed to address this gap by creating an accurate and thorough training program that uses VM software to simulate real-world phishing scenarios, offering hands-on training in a secure setting.

---

## Key Objectives

* **Simulate Phishing Attacks:** Create realistic phishing scenarios within a virtualized environment (e.g., Kali Linux with SEToolkit).
* **Educate Employees:** Develop training materials to teach employees how to differentiate between legitimate and malicious emails, and how to respond to phishing attempts.
* **Hands-on Training:** Provide a practical, interactive experience for users to apply their knowledge in a controlled simulation.
* **Mitigation Strategies:** Equip employees with the skills to mitigate a phishing attack if they accidentally interact with a malicious email.

---

## Technologies and Tools Used

* **Virtualization Software:** Parallels (also considered VMware, VirtualBox)
* **Virtual Machines:** Kali Linux (for attack simulation), Email server
* **Phishing Simulation Software:** SEToolkit in Kali Linux
* **Phishing Templates:** Custom-created templates and those available in SEToolkit.
* **Training Materials:** Educational modules, user guides, policies, and procedures.

---

## Project Implementation and Challenges

The project involved a structured approach from research and scenario development to implementation and testing. A significant challenge encountered was related to email security systems (e.g., Gmail) blocking third-party accounts, which was resolved through thorough research and using alternative SMTP servers.

The project culminated in a hands-on training module that demonstrated the simulation on a virtual machine and a complementary training module on a website.

---

## Outcomes and Applicability

This project resulted in a practical training solution that enhances cybersecurity preparedness. Its applicability extends to:
* **Employee Training:** Providing effective, experiential learning for employees.
* **Compliance:** Helping organizations meet cybersecurity training compliance requirements.
* **Scalability:** The VM-based approach can be scaled to train various departments or larger workforces.
* **Cost-Effectiveness:** Offering a more engaging and potentially more effective training method compared to some traditional solutions.
* **Industry Relevance:** Directly addressing a critical and evolving threat in the cybersecurity landscape.

---

## Lessons Learned

Through this project, I gained a deeper appreciation for the complexities of cybersecurity training and the role of VMs in creating realistic simulation environments. I also learned the importance of thorough planning, continuous monitoring, and effective communication with stakeholders. The experience highlighted the need to anticipate technical intricacies and address potential user skepticism early in the training process.

