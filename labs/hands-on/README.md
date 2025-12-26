

  # ATT&CK Hands-On Labs (Network Discovery & Connections)

This folder contains hands-on labs that map **real network activity and logs** to specific **MITRE ATT&CK techniques**.  
Each lab demonstrates how attacker behavior appears in **Sysmon logs, Windows Firewall logs, and network activity**, and how defenders can detect it.

These exercises simulate **early-stage attacker reconnaissance and discovery**, which commonly precede lateral movement or exploitation.

---

## Lab Environment

- **Attacker:** Kali Linux (192.168.56.102)  
- **Target:** Windows 10 (192.168.56.101)  
- **Hypervisor:** VirtualBox (Host-Only Network)  
- **Logging Enabled:**
  - Sysmon
  - Windows Firewall (pfirewall.log)

---

## Completed Techniques

### ✅ T1046 — Network Service Discovery
**Technique:** Network scanning to identify open ports and services.

- Tool used: `nmap -A`
- Evidence:
  - Firewall DROP logs for ports **135, 139, 445**
  - Sysmon Event ID 3 (network connections)
- Purpose:
  - Identify exposed services (SMB, RPC, NetBIOS)

📄 File: `T1046-network-scanning.md`

---

### ✅ T1018 — Remote System Discovery
**Technique:** Identifying live hosts on the network before deeper scanning.

- Tool used: `nmap -sn`
- Evidence:
  - Nmap reporting host as **up**
  - ICMP-related activity in firewall logs
- Notes:
  - Windows Firewall does not always log IPv4 ICMP Echo traffic by default
  - IPv6 ICMP and multicast traffic still demonstrates discovery behavior

📄 File: `T1018-remote-system-discovery.md`

---

| Technique | Name | Status | Evidence |
|----------|------|--------|----------|
|<a href="https://github.com/omotara100/mitre-attack-threat-mapping/blob/main/labs/hands-on/T1046-network-scanning.md">**T1046**</a> | Network Service Discovery | ✅ Completed | Sysmon, Firewall, Nmap |
| **T1018** | Remote System Discovery | ✅ Completed | ICMP logs, Firewall |
| **T1049** | System Network Connections | ✅ Completed | Netcat logs, Sysmon |

---

### ✅ T1049 — System Network Connections
**Technique:** Observing how systems respond to connection attempts.

- Tool used: `nc`
- Result:
  - Connection attempt to port 80 returned **Connection refused**
- Evidence:
  - Network-level behavior showing service is not listening
- Purpose:
  - Attackers test connectivity before exploitation or lateral movement

📄 File: `T1049-network-connections.md`

---

## Why These Techniques Matter

These techniques represent **early attacker behavior**:

1. **T1018** — Find live systems  
2. **T1046** — Discover services  
3. **T1049** — Test network connections  

Together, they form a **reconnaissance and discovery chain** commonly observed in real intrusions.

Detecting these steps early can prevent:
- Credential theft
- Lateral movement
- Ransomware deployment

---

## Detection & Defensive Takeaways

- Monitor **bursts of network activity** from single internal hosts
- Alert on:
  - Multiple ports probed in short time windows
  - Repeated ICMP or host discovery behavior
  - Connection attempts to closed or uncommon ports
- Correlate:
  - Firewall logs
  - Sysmon Event ID 3
  - IDS/IPS signatures (e.g., Nmap detection)

---

## Next Steps

Planned continuation of this project includes:

- Writing **Sigma detection rules**
- Creating **SIEM detection queries**
- Building **threat hunting playbooks**
- Mapping logs to **MITRE ATT&CK heatmaps**

---

## Screenshots

All screenshots referenced in these labs are stored in the `screenshots/` directory and linked directly in each technique file.

