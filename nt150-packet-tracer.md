---
layout: default
title: "NT-150 Packet Tracer Assignment"
---

# 🌐 NT-150 Packet Tracer Assignment

**Course:** NT-150 Computer Networking  
**Instructor:** Faith Olajide (Student Submission)  

---

## Objective
Simulate and configure a small computer network using **Cisco Packet Tracer** to practice real-world networking skills.

---

## Steps Performed
1. Created network topology with:  
   - 2 PCs  
   - 1 Switch  
   - 1 Router  
2. Configured **IP addressing** for each device.  
3. Verified connectivity using the `ping` command.  
4. Tested communication between end devices through router interface configuration.  
5. Explored VLAN setup to segment traffic.  

---

## Key Commands
```bash
Router> enable
Router# configure terminal
Router(config)# interface g0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
