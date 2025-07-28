# Lab 4: Brute Force Attack Investigation & IP Block via Microsoft Defender

This lab documents a real brute-force login attempt detected on my Azure VM on July 25, 2025. Using Microsoft Sentinel and Defender for Endpoint, I investigated the incident, identified the malicious IP address, and blocked it via custom indicator.
	💡 This exercise helped reinforce incident response workflows: detection → investigation → mitigation.

## Steps Overview
### 1. Detection and Alert:
- Created a custom analytics rule in Sentinel to detect multiple failed login attempts.
- Linked VM logs to Sentinel via Log Analytics Workspace.
- Received email alert from Microsoft Defender for Endpoint on **July 25, 2025**.


### 2. Investigation in Sentinel:
- Investigated the incident: entity details, IPs, login attempts.
- Queried SecurityEvent table for Event ID 4625 (failed login)
- Found multiple failed login attempts from IP 77.223.102.227
- Validated that the alert was triggered by a real attack.
- Screenshot of Kusto query + results

### 3. IP Origin:
Checked IP using external tool → Located in Russia, Selectel network

### 4. Defender for Endpoint Response:
- Navigated to alert
- Added the IP as a custom network indicator and set to "Block"
- Screenshot of the indicator creation

## 🔧 Tools Used
- Microsoft Sentinel
- Microsoft Defender for Cloud
- Log Analytics Workspace
- Azure VM

## 🧠 Key Learning Outcomes
- Hands-on detection of real-world brute force behavior.
- Use of Sentinel analytics rules and incident investigation.
- Better understanding of attacker patterns and log signals.
  
