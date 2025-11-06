# Week 2: Kali Linux Agent Monitoring

## Objective
Install and configure a Wazuh agent on a Kali Linux VM to collect host-based telemetry and forward it to the Wazuh manager. Activate auditd for system call logging and demonstrate detection of privileged commands and network scanning activity.

## Steps Taken
- Verified network connectivity between the Kali VM and Wazuh server using `ping`.
- Installed the Wazuh agent on Kali using the Debian package and configured it to connect to the manager at `192.168.19.129`.
- Enabled and started the `wazuh-agent` service and confirmed the agent appeared as **Active** in the Wazuh dashboard.
- Installed and enabled the `auditd` service to capture security auditing events.
- Edited the agent configuration (`ossec.conf`) to monitor `/var/log/syslog`, `/var/log/auth.log`, and `/var/log/audit/audit.log`.
- Added custom rules on the Wazuh manager to detect `sudo` and `nmap` execution events.
- Generated test events on Kali (creating a user, running `sudo` commands, and performing an `nmap` scan) and verified that alerts appeared in the Wazuh Threat Hunting dashboard.

## Results
- The Kali agent successfully registered with the manager and transmitted logs.
- Auditd events, privileged command use, and network scanning activity were captured and triggered alerts based on custom rules.
- Screenshots showing the active agent, auditd status, and threat hunting alerts are stored in the `screenshots` folder.

## Lessons Learned
- Kali may require importing the Kali archive signing key and updating the apt sources to install auditd.
- Custom rules can be tuned to watch for specific process names or command patterns in audit logs.
- Always verify connectivity and service status after installing agents or system services.
