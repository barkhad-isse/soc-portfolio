# Week 3 command history

This file lists the commands executed during Week 3 while testing MITRE ATT&CK mapping in Wazuh. Use this as a reference for reproducing the environment and results.

## Commands executed

- `sudo nmap -sS 192.168.19.129`  
  Performed a quick TCP SYN scan against the Wazuh manager to identify open ports.

- `sudo nmap -sS -T4 -p- 192.168.19.129`  
  Ran a full TCP port scan across all 65,535 ports on the Wazuh manager.

- `sudo su -` and `cat /etc/shadow`  
  Became root and accessed a privileged file to generate alerts related to initial access and credential access.

- `exit`  
  Exited the root shell.

- `sudo tail -n 100 /var/log/auth.log`  
  Reviewed authentication logs to verify that activities were logged locally.

### Optional (not required)

- `sudo netstat -tuln` / `sudo ss -tuln`  
  Checked listening ports as part of reconnaissance attempts (did not impact core results).

Note: You can add additional commands here if you experiment further. Be sure to document what you do and why.
