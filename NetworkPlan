Lab Network Plan (Host-only VMnets)

- VMnet2 (Kali <-> Ubuntu):
  - Gateway (Ubuntu ens33): 192.xxx.xxx.xxx
  - Kali attacker: 192.xxx.xxx.xxx

- VMnet3 (Ubuntu <-> Windows):
  - Gateway (Ubuntu ens37): 192.xxx.xxx.xxx
  - Windows victim: 192.xxx.xxx.xxx

Notes:
- Ensure VMnet2 and VMnet3 are host-only or isolated in VMware.
- Ubuntu (Suricata) must have two NICs bridged to the two VMnets.

# Interface Map

- Ubuntu (Suricata)
  - ens33 -> VMnet2 -> Kali -> 192.xxx.xxx.xxx
  - ens37 -> VMnet3 -> Windows -> 192.xxx.xxx.xxx

- Kali (Attacker)
  - eth0/ensX -> VMnet2 -> 192.xxx.xxx.xxx

- Windows (Victim)
  - Ethernet adapter -> VMnet3 -> 192.xxx.xxx.xxx

# Network configuration examples

## Kali (nmcli example)
sudo nmcli con add type ethernet ifname eth0 con-name lab-static ipv4.addresses 192.xxx.xxx.xxx/24 ipv4.gateway 192.xxx.xxx.xxx ipv4.method manual

## Windows (static IPv4 example)
- Use the Windows VM's network adapter settings or PowerShell/Netsh to set IPv4 address 192.xxx.xxx.xxx/24 with gateway 192.xxx.xxx.xxx.

