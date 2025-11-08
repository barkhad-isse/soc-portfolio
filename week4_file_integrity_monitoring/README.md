# Week 4 — File Integrity Monitoring (FIM)

## Objective
In week 4, we enabled File Integrity Monitoring (FIM) on the Kali agent and verified that Wazuh detects file creation, modification, and deletion. This demonstrates how the agent monitors critical directories and reports changes back to the SIEM.

## Environment
- **Wazuh Server**: Ubuntu VM at 192.168.19.129
- **Agent**: Kali Linux VM 

## Steps Performed
1. **Create test directory**: Created `/home/kali/fim-test` to monitor file changes.
2. **Verify agent status**: Confirmed that the Wazuh agent was running.
3. **Ensure FIM active**: Verified that Wazuh's syscheck module monitors default system paths and the new test directory.
4. **Generate file events**: Created, modified, and deleted files inside `/home/kali/fim-test`.
5. **Review FIM logs**: Checked `/var/ossec/logs/ossec.log` for syscheck entries.
6. **View alerts in Dashboard**: Opened Wazuh Dashboard → File Integrity Monitoring to see alerts for file changes.

## Findings
- Wazuh recorded file creation, modification, and deletion events from the Kali agent.
- The syscheck module scanned system paths and the test directory and produced alerts.
- In the dashboard, alerts were associated with agent **kali** and user **root**.

## Evidence
The File Integrity Monitoring dashboard showing the detected file changes:
<img width="1913" height="902" alt="Screenshot 2025-11-08 174628" src="https://github.com/user-attachments/assets/7c409c2d-0770-4ca0-b9fc-81828ccd7e1b" />

## Summary
This week demonstrated how Wazuh's file integrity monitoring detects file changes on monitored endpoints. After enabling the syscheck module and generating test file activity, Wazuh successfully logged and displayed the events in the dashboard.
