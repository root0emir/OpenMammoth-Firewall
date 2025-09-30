# OpenMammoth Firewall 

**Developer:** root0emir  
**License:** GNU General Public License v3.0  
**Version:** 1.0

---

## 📜 Overview

OpenMammoth Firewall (O.M. Firewall) is an , **iptables-based firewall** designed for Linux systems.  
It provides layered protection against network attacks, unauthorized access, and malicious traffic while preserving normal internet connectivity.

Features include:  
- SYN flood protection  
- Rate limiting  
- Port scan detection with logging  
- Advanced ICMP, UDP, and TCP packet protection  
- Tor detection and prevention  
- Logging of suspicious network activities  
- Anti-spoofing and anti-fragmentation rules  
- Enhanced SSH security  
- HTTP/HTTPS connection limiting  

---

## ⚙️ Features

### 1. Firewall Activation
- Full iptables protection  
- Loopback traffic allowance  
- Established connection protection  
- ICMP control with Ping-of-Death mitigation  
- TCP and UDP advanced protections  
- SYN flood and connection rate limiting  
- Port scan detection  
- TCP MSS clamping  

### 2. Firewall Logging
- Detailed logging for suspicious and invalid packets  
- Logs saved to `/var/log/openmammoth-firewall.log`  
- Optional logging enable/disable from menu  

### 3. Tor & VPN Detection
- Multi-layered Tor traffic detection:  
  - Tor API check (`check.torproject.org`)  
  - DNS leak detection  
  - Tor process & port detection  
  - Tun/Tap interface inspection  
  - Public IP Tor exit node check  
- Firewall will **not activate** if Tor traffic is detected  

### 4. Firewall Status Reporting
- Displays active rule count  
- Input policy verification  
- Checks SYN flood protection, rate limiting, mangle table rules, and connection tracking  
- Shows system memory and CPU usage  

### 5. User-friendly Interface
- Interactive menu  
- Color-coded status messages  
- Safe internet connection preservation  

---

## 📝 Requirements

- Linux system with `iptables` installed  
- Root privileges (`sudo`)  
- Optional: `curl`, `dig`, `netstat` for Tor detection  

---

## 🚀 Installation

1. Clone the repo   
```bash
https://github.com/root0emir/OpenMammoth-Firewall.git
```
2. Make it executable:
```bash
chmod +x openmammoth-firewall
```
3. Run as root:
```bash
sudo ./openmammoth-firewall.sh
```

## 📂 Menu Options

| Option | Description |
|--------|-------------|
| 1      | Enable O.M. Firewall – Activate firewall protection |
| 2      | Disable O.M. Firewall – Deactivate firewall |
| 3      | Status O.M. Firewall – View current firewall status and stats |
| 4      | Enable Firewall Logs – Enable detailed logging |
| 5      | Disable Firewall Logs – Disable logging |
| 6      | Exit – Close the firewall interface |

---

## 🛡️ Security Details

- **Default Policies:** INPUT & FORWARD → DROP, OUTPUT → ACCEPT  
- **Loopback Traffic:** Always allowed  
- **SSH Protection:** Rate limiting & brute-force prevention  
- **ICMP Protection:** Echo-request limits & dangerous ICMP types blocked  
- **UDP Protection:** Rate limiting & invalid packets blocked  
- **Anti-spoofing:** Blocks private/reserved IP ranges  
- **Port Scan Detection:** Logs and blocks port scans  
- **Tor Traffic Prevention:** Ensures firewall rules don’t interfere with anonymization networks  

---

## 🧾 Logging

- **Primary log file:** `/var/log/openmammoth-firewall.log`  
- **Optional kernel logs:** `/var/log/kern.log` or `/var/log/messages`  
- **Logs include:**  
  - Firewall activations/deactivations  
  - Detected Tor traffic  
  - Invalid packets  
  - Port scan attempts  

---
## 🔧 Usage Example

```bash
sudo ./openmammoth-firewall
```

- Check the menu and choose 1 to enable the firewall.

- Optionally enable logging via 4.

- Monitor system and network traffic using 3.


---

⚖️ License

OpenMammoth Firewall is licensed under GNU General Public License v3.0.
You may redistribute and/or modify it under the terms of the GPLv3.

This program is distributed in the hope that it will be useful, but without any warranty.

---

WARNING:

The firewall is Tor-aware. If Tor traffic is detected, the firewall will prevent activation to avoid breaking anonymization networks.

---
