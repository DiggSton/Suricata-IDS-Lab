
# Minimal sample - AF_PACKET section only (paste into your /etc/suricata/suricata.yaml)
# Replace other parts in your config as needed. Ensure indentation is 2 spaces.
af-packet:
  - interface: ens33
    cluster-id: 99
    cluster-type: cluster_flow
    defrag: yes

  - interface: ens37
    cluster-id: 100
    cluster-type: cluster_flow
    defrag: yes

# NOTE: this is only the capture block. The full suricata.yaml also contains
# rule-files, outputs, logging, etc. Use `sudo suricata -T -c /etc/suricata/suricata.yaml`
# to test the overall config after editing.
