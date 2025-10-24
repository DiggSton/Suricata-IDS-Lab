# VM Setup Guide

This file contains step-by-step instructions to configure the three VMs used in this lab.

## Network plan (example)
- VMnet2: Kali <-> Ubuntu (attacker subnet) — 192.168.XX.XX/24
- VMnet3: Ubuntu <-> Windows (victim subnet) — 192.168.XX.XX/24

## Ubuntu (Suricata) Setup Summary
1. Ensure Ubuntu VM has two NICs: one connected to VMnet2 and one to VMnet3.
2. Install Suricata:
   ```bash
   sudo apt update
   sudo apt install -y suricata jq
3.	Copy ubuntu-suricata/suricata.yaml.sample to /etc/suricata/suricata.yaml and edit interfaces (ens33, ens37).
4.	Place ubuntu-suricata/local.rules into /var/lib/suricata/rules/local.rules.
5.	Test config:
6.	sudo suricata -T -c /etc/suricata/suricata.yaml
7.	sudo systemctl restart suricata
8.	sudo systemctl status suricata
Kali (Attacker) Setup Summary
1.	Configure static IP or use DHCP on VMnet2: 192.168.XX.XX/24 gateway 192.168.XX.XX.
2.	Install required tools:
3.	sudo apt update
4.	sudo apt install -y nmap hydra wordlists netcat
Windows (Victim) Setup Summary
1.	Assign static IP on VMnet3: 192.168.XX.XX/24.
2.	Enable RDP (or install OpenSSH) for test services (see scripts in windows-victim/).
3.	Create test accounts for brute-force tests:
4.	net user testuser Password123! /add
YAML
# Test Results

Include short summaries and sample outputs here. Replace or expand with your actual outputs.

## Example: Fast log excerpts
- ICMP scan detected (Priority 3)
- Nmap SYN scan detected (Priority 3)
- SSH brute force detected (Priority 2)
- RDP attempt (Priority 1)
See `logs/sample-fast.log` for example entries.

## Notes
- All tests were run in an isolated VM host-only environment.
- Timestamps in sample logs have been sanitized.

