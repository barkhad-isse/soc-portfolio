# Week 4 — File Integrity Monitoring Setup

## Objective 
The goal for Week 4 was to enable and verify File Integrity Monitoring (FIM) on the Wazuh agent running on the Kali VM.
By simulating file creations, modifications and deletions, we proved that Wazuh correctly logs changes and forwards alerts to the SIEM.

## Environment

Wazuh server - Ubuntu VM (192.168.19.129) - Runs the Wazuh manager, indexer, and dashboard
Wazuh agent -	Kali VM -	Monitors the endpoint and sends telemetry to the manager
Test directory - /home/kali/fim-test - A dedicated folder used to trigger FIM events

## Steps Performed

- Verified agent status
- Ensured the Wazuh agent was up and running on the Kali VM
- Created a folder on Kali to use for FIM testing
- Created, modified and deleted a file to trigger integrity alerts
- Confirmed that the agent’s syscheck (FIM) module recorded the activity
- Using the Wazuh web UI, navigated to Overview, then File Integrity Monitoring and verified alerts indicating file creations, modifications and deletions on the kali agent.

## Findings
- The Wazuh agent correctly monitored the /home/kali/fim-test directory.
- Creating, appending to and deleting testfile.txt generated Integrity checksum alerts that were visible under File Integrity Monitoring in the dashboard.
- The alerts listed the affected file, the action (added, modified, deleted), the user (root), and the agent name (kali).

## Evidence

![FIM Dashboard Results]
<img width="1913" height="902" alt="Screenshot 2025-11-08 174628" src="https://github.com/user-attachments/assets/8e4e7ca5-39a6-433c-97d8-bd8c9970c73a" />
This image should show the File Integrity Monitoring dashboard with alerts indicating modifications in the fim-test directory.

## Summary

### By the end of Week 4 we had:

- Verified that the Wazuh agent was running and communicating with the manager.
- Configured a specific directory to monitor for file changes.
- Demonstrated that Wazuh detects creations, modifications and deletions in real time.
- Recorded the results in both log files and the dashboard.
These steps complete the File Integrity Monitoring lab and provide evidence that the SIEM is ready to detect file tampering events.
