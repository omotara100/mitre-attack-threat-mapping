# Threat Hunting – T1018 Remote System Discovery

## Objective
Detect hosts performing ICMP-based discovery to identify live systems.

---

## Hypothesis
An attacker may use ping sweeps to identify reachable hosts before further scanning.

---

## Data Sources
- Windows Firewall ICMP logs
- Network telemetry
- IDS / ICMP alerts

---

## Hunting Queries / Logic
- Repeated ICMP Echo Requests from one source
- ICMP traffic to multiple internal hosts
- Host discovery without follow-on legitimate traffic

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

## MITRE Mapping
- Tactic: Discovery
- Technique: T1018 – Remote System Discovery
