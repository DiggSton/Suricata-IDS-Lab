# Local lab rules - safe, intentionally broad for demonstration.
# Place this file at /var/lib/suricata/rules/local.rules (or your default-rule-path)

alert icmp any any -> any any (msg:"LAB ICMP - PRIORITY 3"; sid:1200001; rev:1; priority:3;)
alert tcp any any -> any 22 (msg:"LAB SSH attempt - PRIORITY 2"; sid:1200002; rev:1; priority:2;)
alert tcp any any -> any 3389 (msg:"LAB RDP attempt - PRIORITY 1"; sid:1200003; rev:1; priority:1;)

# Example threshold rule to detect repeated SSH attempts (adjust values for lab)
alert tcp any any -> any 22 (msg:"LAB SSH Brute Threshold"; sid:1200100; rev:1; priority:2; detection_filter: track by_src, count 5, seconds 60;)
