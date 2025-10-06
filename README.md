# Suricata-IDS-Lab
Lab demonstrating IDS  
# Suricata(Ubuntu)/Windows/Kali IDS Lab

**Small isolated lab** demonstrating Suricata IDS/IPS monitoring with an Ubuntu sensor (dual-NIC), a Kali attacker, and a Windows victim. This repo includes configuration snippets, test rules, scripts, and a network diagram.

---

## 🔹 Overview
This project demonstrates how to set up and use **Suricata IDS/IPS** to monitor malicious activity in a small virtualized network. The lab includes three machines running in VMware:

- **Ubuntu Server** (Suricata IDS)
- **Kali Linux** (attacker)
- **Windows 10** (victim)

The goal was to generate and detect network traffic such as **Nmap scans** and **SSH brute force attempts**, and confirm alerts in Suricata’s logs.

> ⚠️ **Safety:** Run everything only inside an isolated lab network (Host-Only / private VMnets). Do **not** run these tools against public or production systems.

---
