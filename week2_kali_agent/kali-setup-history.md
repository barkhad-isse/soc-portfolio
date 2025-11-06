# Kali agent and audit setup history

## Install and register Wazuh agent on Kali

- curl -so wazuh-agent.deb https://packages.wazuh.com/4.x/apt/pool/main/w/wazuh-agent/wazuh-agent_4.14.0-1_amd64.deb
- sudo WAZUH_MANAGER='192.168.19.129' dpkg -i ./wazuh-agent.deb
- sudo systemctl enable wazuh-agent
- sudo systemctl start wazuh-agent
- sudo systemctl status wazuh-agent

## Fix missing signing key and update package lists (Kali rolling)

- sudo apt install gnupg -y
- sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys ED65462EC8D5E4C5
- sudo apt update

## Install auditd and audit dispatch plugins

- sudo apt install -y auditd audispd-plugins
- sudo systemctl enable --now auditd
- sudo systemctl status auditd

## Troubleshoot package repository (optional, if auditd packages cannot be found)

- sudo apt clean
- sudo rm -rf /var/lib/apt/lists/*
- echo "deb http://http.kali.org/kali kali-rolling main non-free non-free-firmware contrib" | sudo tee /etc/apt/sources.list
- sudo apt update

## Restart Wazuh agent after configuration changes

- sudo systemctl restart wazuh-agent
