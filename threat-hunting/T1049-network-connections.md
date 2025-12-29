# Threat Hunting – T1049 System Network Connections

## Objective
Detect suspicious outbound or lateral network connections that indicate reconnaissance or probing.

---

## Hypothesis
An attacker may test connectivity to services to understand reachable systems and firewall behavior.

---


## Data Sources
- Sysmon Event ID 3
- Firewall logs
- NetFlow
- SIEM

---

## Hunting Queries / Logic
- Repeated connection attempts to a single port
- Connection attempts resulting in RESET or DROP
- Use of uncommon tools (netcat)

---

## Hunt Steps
1. Identify unusual outbound connection attempts.
2. Look for failed connection attempts (connection refused).
3. Correlate with earlier discovery activity.

---

## Example Indicators
- Netcat-style connection attempts
- Connection attempts to unexpected ports
- Repeated failures to same destination
  
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

## Expected Findings
- Benign: troubleshooting, service checks
- Malicious: probing, C2 preparation

---

## Outcome
- ☐ True Positive
- ☐ False Positive
- ☐ Needs More Data

---

## MITRE Mapping
- Tactic: Discovery
- Technique: T1049 – System Network Connections
