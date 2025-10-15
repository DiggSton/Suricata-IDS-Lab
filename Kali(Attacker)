#!/bin/bash
# Full lab test script (Kali) - run in the attacker's shell.
# WARNING: Run only in isolated lab.

VICTIM=192.168.XX.XX

echo "1) Ping test (ICMP)"
ping -c 3 $VICTIM

echo "2) Quick Nmap SYN scan on key ports"
sudo nmap -sS -Pn -p 22,80,139,445,3389 -T4 $VICTIM

echo "3) SSH fail loop (generate auth failures)"
for i in {1..6}; do ssh -o ConnectTimeout=2 wronguser@$VICTIM exit; done

echo "4) RDP connect attempts (non-destructive)"
for i in {1..8}; do nc -vz $VICTIM 3389; done

echo "Done. Check Suricata fast.log on the sensor."

 HYDRA
#!/bin/bash
# Small hydra test with a short wordlist
VICTIM=192.168.XX.XX
USER=testuser
WORDLIST=/tmp/testpw.txt

cat > $WORDLIST <<'EOF'
password
Password123!
admin
letmein
123456
EOF

echo "Running hydra (small test)..."
hydra -l $USER -P $WORDLIST ssh://$VICTIM -t 4

# Kali Attacker Notes

- Ensure `nmap`, `hydra`, `netcat` are installed: `sudo apt install -y nmap hydra netcat`
- Use small wordlists for demonstration to avoid lengthy runs: see hydra-test.sh
- Only run tests in isolated lab; do not run hydra or scans against Internet hosts.
