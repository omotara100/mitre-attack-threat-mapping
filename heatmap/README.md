# MITRE ATT&CK Heatmap

## Overview
This heatmap represents MITRE ATT&CK techniques that were **observed, validated, and detected**
during hands-on SOC labs using Sysmon, Windows Firewall logs, and network traffic.

The goal is to demonstrate **defender visibility** rather than attacker simulation.

---

## Heatmap Legend
- 🟩 **Observed & Logged** — Confirmed in Sysmon / Firewall logs
- 🟧 **Detection Created** — Sigma or SIEM detection written
- ⬜ **Not Covered Yet**

---

## Covered Techniques

| Tactic | Technique ID | Technique Name | Status | Evidence |
|------|------------|---------------|--------|---------|
| Discovery | T1046 | Network Service Discovery | 🟩🟧 | Nmap scan + Sysmon ID 3 |
| Discovery | T1018 | Remote System Discovery | 🟩🟧 | ICMP / Host discovery |
| Discovery | T1049 | System Network Connections | 🟩🟧 | Netcat connection attempt |

---

## Why This Matters
Heatmaps help SOC analysts:
- Identify visibility gaps
- Prioritize detection engineering
- Map alerts to attacker behavior
- Communicate coverage to stakeholders

This heatmap reflects **real logs**, not theory.
