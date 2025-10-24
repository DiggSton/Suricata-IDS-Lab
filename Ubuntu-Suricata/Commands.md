#!/bin/bash
# Start Suricata on the two lab interfaces in background
# Update interface names if yours differ.

IF1=ens33
IF2=ens37
CONF=/etc/suricata/suricata.yaml

echo "Stopping any running Suricata..."
sudo pkill suricata || true
sleep 1

echo "Starting Suricata on $IF1 and $IF2..."
sudo suricata -c "$CONF" -i "$IF1" -i "$IF2" -D

echo "Suricata started. Check logs with: sudo tail -f /var/log/suricata/fast.log"
#!/bin/bash
echo "Stopping Suricata..."
sudo systemctl stop suricata || sudo pkill suricata || true
echo "Stopped. Remove any leftover pid file if necessary: sudo rm -f /var/run/suricata.pid"

# Ubuntu Suricata Notes

- Default rule directory used in this repo: `/var/lib/suricata/rules`
- If your suricata.yaml uses a different `default-rule-path`, copy local.rules there.
- Test config: `sudo suricata -T -c /etc/suricata/suricata.yaml`
- Logs:
  - Fast alerts: `/var/log/suricata/fast.log`
  - Runtime log: `/var/log/suricata/suricata.log`
