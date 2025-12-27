# Detection Rules

This folder contains detection content created as part of my SOC analyst hands-on project.

## Purpose
These Sigma rules are designed to detect attacker discovery behavior mapped to MITRE ATT&CK techniques.

## Techniques Covered
- **T1018** – Remote System Discovery (Ping Sweeps)
- **T1046** – Network Service Discovery (Nmap Scanning)
- **T1049** – System Network Connections



# Detection Engineering – Sigma Rules

## Overview
This folder contains Sigma detection rules mapped to MITRE ATT&CK techniques.
The rules are based on hands-on lab activity and real Windows telemetry.

Each rule is:
- MITRE-aligned
- Based on Sysmon and Firewall logs
- Designed for SIEM platforms

---

## Included Techniques
- T1046 – Network Service Discovery
- T1018 – Remote System Discovery
- T1049 – System Network Connections

---

## Data Sources
- Sysmon
- Windows Firewall
- Network telemetry

---

## Usage
These rules can be converted for SIEM platforms such as:
- Splunk
- Elastic
- Sentinel
  
---

## Notes
Rules are marked as experimental and should be tuned to reduce false positives in production environments.

---

## Disclaimer
These rules are lab-focused and should be tuned before production use.
False positives are expected in environments with scanning or monitoring tools.

---

## Author
SOC Project – Hands-on Detection Engineering
