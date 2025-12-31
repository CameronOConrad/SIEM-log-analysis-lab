

# SIEM Log Analysis Home Lab (Splunk)

## Overview
This project demonstrates the setup and use of a Security Information and Event Management (SIEM) system, utilizing Splunk, in a virtualized home lab. Logs from both Windows and Linux systems are centrally collected and analyzed to detect suspicious activity such as failed login attempts and potential reconnaissance behavior.

This lab builds on foundational networking and security concepts, focusing on real-world SOC analyst tasks such as log ingestion, detection logic, and troubleshooting.

---

## Objectives
- Deploy a SIEM using Splunk Enterprise (Free)
- Collect and analyze logs from Windows and Linux systems
- Detect suspicious authentication and network activity
- Practice real-world SIEM troubleshooting
- Document findings in a clear, professional format

---

## Lab Environment

### Virtual Machines
| System | Role |
|------|-----|
| Windows 10 | Splunk Server & Log Source |
| Ubuntu Linux | Log Source (SSH, authentication logs) |

### Tools Used
- VirtualBox
- Splunk Enterprise (Free)
- Splunk Universal Forwarder
- Windows Event Logs
- Linux authentication logs (`/var/log/auth.log`)

---

## Architecture Overview
- Ubuntu VM
- Splunk Universal Forwarder
- Splunk SIEM (Windows VM)
- Windows VM
- Splunk SIEM

  
All systems are connected using a NAT Network to allow VM-to-VM communication while remaining isolated from the host network.

---

## Log Sources Ingested

### Windows
- Security Event Logs
- System Event Logs
- Application Logs

### Linux
- SSH authentication logs
- Failed login attempts

---

## Detection Use Cases

### 1. Failed Windows Login Attempts
Detects repeated failed authentication attempts, which may indicate brute-force activity.

### 2. Failed Linux SSH Authentication
Detects multiple failed SSH logins, a common attack against Linux systems.

### 3. Event Spike Detection (Reconnaissance Indicator)
Detects abnormal spikes in event volume, which may indicate scanning or enumeration activity.

Detection queries are documented in `queries.md`.

---

## Evidence
The `screenshots` directory contains:
- Splunk dashboard showing log ingestion
- Failed Windows login detection results
- Failed Linux SSH authentication results
- Event spike detection during simulated scanning activity

---

## Key Skills Demonstrated
- SIEM deployment and configuration
- Log ingestion and normalization
- Writing detection logic in Splunk SPL
- Troubleshooting log forwarding issues
- Security event analysis
- Clear technical documentation

---

## Lessons Learned
- SIEMs require proper log forwarding and network configuration
- Logs must be generated to validate detections
- Detection logic often needs adjustment based on available data
- Troubleshooting is a core SOC analyst skill

---

## Future Improvements
- Add alerting and thresholds
- Integrate additional log sources
- Visualize detections using Splunk dashboards
- Expand lab with IDS/IPS tools

---

## Disclaimer
This project was created for educational purposes in a controlled lab environment.
