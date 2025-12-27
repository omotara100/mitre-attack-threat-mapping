# Detection Rules

This folder contains detection content created as part of my SOC analyst hands-on project.

## Purpose
These Sigma rules are designed to detect attacker discovery behavior mapped to MITRE ATT&CK techniques.

## Techniques Covered
- **T1018** – Remote System Discovery (Ping Sweeps)
- **T1046** – Network Service Discovery (Nmap Scanning)
- **T1049** – System Network Connections

## Usage
These rules can be converted for SIEM platforms such as:
- Splunk
- Elastic
- Sentinel

## Notes
Rules are marked as experimental and should be tuned to reduce false positives in production environments.
