# 🧪 Hands-On MITRE ATT&CK Labs

This folder contains practical, real-world exercises mapped directly to MITRE ATT&CK techniques.  
All labs were performed using:

- Kali Linux (attacker machine)
- Windows 10 with Sysmon & Firewall logging enabled
- MITRE ATT&CK v14 mapping
- Real logs: Sysmon, Windows Firewall, Nmap output

These labs demonstrate how attackers behave, how systems generate telemetry, and how SOC analysts analyze and detect malicious activity.

---

## 🔥 Completed Techniques

| Technique | Name | Status | Evidence |
|----------|------|--------|----------|
|<a href="https://github.com/omotara100/mitre-attack-threat-mapping/blob/main/labs/hands-on/T1046-network-scanning.md">**T1046**</a> | Network Service Discovery | ✅ Completed | Sysmon, Firewall, Nmap |
| **T1018** | Remote System Discovery | ✅ Completed | ICMP logs, Firewall |
| **T1049** | System Network Connections | ✅ Completed | Netcat logs, Sysmon |

---

## 📁 Files in This Folder

- **T1046-network-scanning.md**  
  Aggressive Nmap service scan → Sysmon & Firewall detection.

- **T1018-remote-system-discovery.md**  
  ICMP host discovery (ping sweep).

- **T1049-network-connections.md**  
  Netcat TCP connection attempts → allow/drop behavior.

- **/screenshots/**  
  Contains captured evidence from real logs.
