# Threat Hunting – T1018 Remote System Discovery

## Objective
Detect hosts performing ICMP-based discovery to identify live systems.

---

## Hypothesis
An attacker may be identifying live hosts within the network using ICMP or host discovery scans.

---

## Data Sources
- Windows Firewall Logs (ICMP)
- Sysmon Event ID 3
- Network telemetry
- SIEM logs

---

## Hunting Queries / Logic
- Repeated ICMP Echo Requests from one source
- ICMP traffic to multiple internal hosts
- Host discovery without follow-on legitimate traffic

---

## Hunt Steps
1. Look for repeated ICMP Echo Requests from one internal host.
2. Identify host discovery scans (nmap -sn behavior).
3. Correlate ICMP activity with later port scans.

---

## Example Indicators
- ICMP traffic bursts
- Host discovery followed by T1046 activity
- Discovery from non-admin endpoints
---

## Expected Findings
- ICMP Echo Request / Reply patterns
- Nmap host discovery behavior
- Short bursts of ICMP traffic

---

## False Positives
- Network troubleshooting
- Monitoring systems
- Backup systems

---

## Response Actions
- Validate source system purpose
- Correlate with port scanning activity (T1046)
- Monitor for lateral movement

---

## Outcome
- ☐ True Positive
- ☐ False Positive
- ☐ Needs More Data
- 
---

## MITRE Mapping
- Tactic: Discovery
- Technique: T1018 – Remote System Discovery
