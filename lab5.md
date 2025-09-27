---
layout: default
title: "Lab 5 - Two-Factor Authentication (IAE 250)"
---

# 🔐 Lab 5 - Two-Factor Authentication (IAE 250)

**Course:** IAE-250 Comprehensive Computer & Network Security  
**Prepared by:** Faith Olajide  
**Professor:** Richard Hansen  

---

## Abstract  
Student will be able to authenticate two-factor authentication (2FA) through Google.

---

## Materials
- Ubuntu server  
- Windows server  
- Google Authenticator app  

---

## Methodology
1. Logged into Ubuntu server as `student/student`.  
2. Ran `google-authenticator` to generate QR and secret codes.  
3. Edited PAM login config:  
   ```bash
   sudo nano /etc/pam.d/login
   auth required pam_google_authenticator.so nullok
