# Threat Hunting – T1049 System Network Connections

## Objective
Detect suspicious outbound or lateral network connections that indicate reconnaissance or probing.

---

## Hypothesis
An attacker may test connectivity to services to understand reachable systems and firewall behavior.

---

## Data Sources
- Windows Firewall logs
- Sysmon Event ID 3
- NetFlow / Zeek (if available)

---

## Hunting Queries / Logic
- Repeated connection attempts to a single port
- Connection attempts resulting in RESET or DROP
- Use of uncommon tools (netcat)

---

## Expected Findings
- TCP connection attempts with no data transfer
- Connection refused responses
- Short-lived sessions

---

## False Positives
- Application health checks
- Monitoring probes

---

## Response Actions
- Validate source host activity
- Review command-line usage
- Correlate with discovery activity

---

## MITRE Mapping
- Tactic: Discovery
- Technique: T1049 – System Network Connections
