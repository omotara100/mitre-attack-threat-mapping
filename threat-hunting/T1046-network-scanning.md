# Threat Hunting – T1046 Network Service Discovery

## Objective
Identify internal hosts performing network port scans that resemble reconnaissance activity.

---

## Hypothesis
An attacker or compromised internal host may scan multiple ports on another internal system to identify exposed services.

---

## Data Sources
- Sysmon Event ID 3 (Network Connection)
- Windows Firewall logs (pfirewall.log)
- IDS / Suricata alerts (if available)

---

## Hunting Queries / Logic
- Look for a single Source IP connecting to many destination ports on the same host within a short time window.
- Identify repeated TCP SYN packets with no successful session establishment.

Example logic:
- SourceIp = X
- DestinationIp = Y
- DestinationPort count > 20
- Time window < 60 seconds

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

## MITRE Mapping
- Tactic: Discovery
- Technique: T1046 – Network Service Discovery
