# Week 3 command history



## Configure and verify Auditd

- sudo apt update
- sudo apt install -y auditd audispd-plugins
-  systemctl enable --now auditd
- sudo systemctl status auditd


## Simulate attacker-like behavior

- sudo nmap -sS -T4 -p- 192.168.19.129
- sudo netstat -tuln
- sudo ss -tuln

##Setup Overview

- Ubuntu VM (192.168.19.129) — Hosting the Wazuh Server (Manager + Indexer + Dashboard).
- Kali Linux VM — Running the Wazuh Agent and generating system events.
Both machines were on the same local network and communication was verified via ping.

