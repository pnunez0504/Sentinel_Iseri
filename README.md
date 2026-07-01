# Project Sentinal_Iseri  Raspberry Pi Network IDS + Honeypot 

## Project Overview
Using the Raspberry Pi I have been coding/ tinkering on since middle school, I decided to set up a host Intrusion Detection Syst>

## Tools Used
- **Suricata** as a Network Intrusion Detection System (NIDS)
- **Cowrie** as an SSH honeypot
- **Raspberry Pi 4** sensor platform/ personal Cyber Security Lab

In order to understand how these systems log events, I decided to simulate attacker behavior, and perform multi-sensor correlation similar to>

---

## Architecture

Attacker VM / Windows Laptop
⬇ /n
Raspberry Pi (Suricata + Cowrie)

Suricata monitors the Pi’s **wlan0** interface for inbound/outbound traffic.
Cowrie captures attacker behavior inside a fake SSH shell.

---

## ⚙️ Tools Used
- Suricata IDS
- Cowrie Honeypot 
- ET Open Ruleset
- Raspberry Pi OS
- Nmap
- curl 
- wget 
- SSH client 

---

## 📡 Suricata Configuration

Suricata was configured to monitor the Pi’s wireless interface:

af-packet:
- interface:wlan0
- cluster-id:99
- cluster-type:cluster_flow
Rulset updated using **sudo suricata-update**
---

## Logs used for report

- /var/log/suricata/fast.log - Readable Alerts for context
- /var/log/suricata/eve.json - json content with metadata for other uses
- /var/log/cowrie/cowrie.json -json log for Honeypot
- /var/log/cowrie/tty/ - attacker records and transcripts

---
# Attack Simulations
offensive acticvities were done on my virtual machine I made in class on my personal computer to capture real traffic. The actions are listed below
- Nmap SYN Scan+
- Nmap Version Scan
- Suricata Test Alert
- Outbound Download Through HTTP
- External DNS Query
---
## Suricata Log Analysis

suricata rpoduced alerts for 
- Port Scans
- Suspicious DNS queries
- Outbound HTTP requests
- IDS test signatures

### Nmap Scan Alerts

---
## Cowrie Honeypot Analysis
Used as the **Iseri** (Garifuna for eye) for the project. Captures attacker behavior inside a false SSH shell
