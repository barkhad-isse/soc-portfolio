# Week 3: MITRE ATT&CK Analysis

## Objective

In this week, the focus was on simulating suspicious activity (e.g., network scans) on the Kali Linux VM and verifying that the Wazuh SIEM, running on the Ubuntu VM, can detect and log these events correctly. The goal was to understand how endpoint activities generate alerts and are forwarded to the SIEM.

## Steps Taken

1. Ran host-based activity on the Kali agent to generate logs (e.g., Nmap scans and privileged commands).
2. Opened the MITRE ATT&CK dashboard in Wazuh and refreshed to view recent activity.
3. Reviewed the top tactics and techniques triggered by our actions.

## Results
#### 1. Network Connectivity Check  
Before testing, connectivity between the Kali agent and the Wazuh server was verified.

#### 2. Generate System and Network Events  
Simulated system activity and network scans from Kali to produce detectable events.

#### 3. Auditd Installation and Activation  
Installed and configured auditd to monitor system activity and command executions.

#### 4. Verifying Audit Logging  
Confirmed that auditd was running and collecting logs of recent successful events.

#### 5. Wazuh Agent Verification  
Verified that the Wazuh agent was running and communicating properly with the server.

## Evidence
<img width="1913" height="908" alt="wasuh3" src="https://github.com/user-attachments/assets/e71783d5-0a62-4f80-bf57-b139516bbd93" />


