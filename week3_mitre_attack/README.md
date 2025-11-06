# Week 3 – MITRE ATT&CK Analysis

## Objective

Explore the MITRE ATT&CK dashboard within Wazuh to understand how detected events are mapped to tactics such as Defense Evasion, Privilege Escalation, Initial Access, and Persistence.

## Steps Performed

1. Ran host-based activity on the Kali agent to generate logs (e.g., Nmap scans and privileged commands).  
2. Opened the MITRE ATT&CK dashboard in Wazuh and refreshed to view recent activity.  
3. Reviewed the top tactics and techniques triggered by our actions.

For the full list of commands used during this exercise, see **`week3_mitre_attack/command-history.md`**.

## Findings

The MITRE ATT&CK dashboard showed activity for several tactics:
- **Defense Evasion**
- **Privilege Escalation**
- **Initial Access**
- **Persistence**

Reconnaissance was not displayed by default. The focus of Week 3 was to confirm that Wazuh is properly mapping events to ATT&CK tactics and understanding which behaviors generate detections.

## Evidence

A screenshot has been captured of the MITRE ATT&CK dashboard showing the observed tactics and techniques. Please add the file `mitre_dashboard_overview.png` to this folder and reference it in `screenshots.md`.

## Lessons Learned

- Wazuh can map host-based activity to multiple MITRE ATT&CK tactics out-of-the-box.  
- Additional configuration (e.g., auditd rules or network IDS alerts) might be required to map reconnaissance activities.
