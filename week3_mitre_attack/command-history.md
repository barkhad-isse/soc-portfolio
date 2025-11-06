# Week 3 command history


## Commands executed

Configure and verify Auditd

- sudo apt update
- sudo apt install -y auditd audispd-plugins
-  systemctl enable --now auditd
- sudo systemctl status auditd


Simulate attacker-like behavior

- sudo nmap -sS -T4 -p- 192.168.19.129
- sudo netstat -tuln
- sudo ss -tuln
