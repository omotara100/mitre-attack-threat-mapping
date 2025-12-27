# Threat Hunting – T1046 Network Service Discovery

## Objective
Identify internal hosts performing network port scans that resemble reconnaissance activity.

---

## Hypothesis
An attacker or compromised internal host may scan multiple ports on another internal system to identify exposed services.

---

## ATT&CK Technique
- T1046 – Network Service Discovery

---

## Data Sources
- Sysmon Event ID 3 (Network Connections)
- Windows Firewall Logs (pfirewall.log)
- IDS/IPS (Suricata, Zeek)
- SIEM (Splunk, Sentinel)

---

## Hunting Queries / Logic
- Look for a single Source IP connecting to many destination ports on the same host within a short time window.
- Identify repeated TCP SYN packets with no successful session establishment.
- Correlate firewall DROP events with Sysmon network connection logs.


Example logic:
- SourceIp = X
- DestinationIp = Y
- DestinationPort count > 20
- Time window < 60 seconds

---

## Example Indicators
- Multiple connections to ports 135, 139, 445
- Rapid port enumeration
- Repeated firewall DROP actions

---

## Expected Findings
- Nmap-style scans (ports 135, 139, 445, etc.)
- Firewall DROP or RESET responses
- No corresponding successful logon events

---

## False Positives
- Vulnerability scanners
- IT asset discovery tools
- Monitoring systems

---

## Response Actions
- Identify scanning host owner
- Isolate host if unauthorized
- Review subsequent activity (lateral movement, exploitation)

---

## Outcome
- ☐ True Positive
- ☐ False Positive
- ☐ Needs More Data

---

## MITRE Mapping
- Tactic: Discovery
- Technique: T1046 – Network Service Discovery
