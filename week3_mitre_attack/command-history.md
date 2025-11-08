# Week 3 command history


## Network Connectivity Check
- ping 192.168.19.129

## Simulate Network Activity

- sudo nmap -sS 192.168.19.129
- sudo nmap -sS -T4 -p- 192.168.19.129
 
## Install and Enable Auditd

- sudo apt install -y auditd audispd-plugins
- sudo systemctl enable --now auditd
- sudo systemctl status auditd

## Verify Audit Logs
- sudo ausearch --start recent --success yes | tail -n 20
