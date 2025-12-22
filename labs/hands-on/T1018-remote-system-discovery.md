# T1018 – Remote System Discovery (Ping Sweep)

## Overview
This lab demonstrates MITRE ATT&CK Technique **T1018 – Remote System Discovery**, where an adversary identifies live hosts on a network before performing deeper scanning or exploitation.  
I used Kali Linux to perform a host discovery (ping sweep–style) scan against my Windows 10 machine (**192.168.56.101**).

---

## What I Did
From the Kali VM, I executed an Nmap host discovery scan to determine whether the target system was reachable:

- ICMP Echo Requests (ping)
- Host availability checks only (no port scanning)
- Verification that the target system was online

Target: **192.168.56.101** (Windows)

---

## Firewall Log Evidence
Windows Firewall logging captured ICMP-related network activity associated with host discovery behavior.  
While direct IPv4 ICMP Echo logs from Kali were limited (due to Windows Firewall defaults and VirtualBox networking behavior), the following indicators were observed:

- ICMP traffic associated with system discovery
- Network-layer activity consistent with host probing
- Target host reported as **“up”** in Nmap results

This behavior aligns with **T1018**, where attackers confirm which systems are alive before moving to service discovery (T1046) or lateral movement.

---

## Commands Used

nmap -sn 192.168.56.101

---

## Screenshots / files 
- <a href="https://github.com/omotara100/mitre-attack-threat-mapping/blob/main/screenshots/kali-ping-sweep.PNG"> kali-ping-sweep.png</a> — Nmap host discovery output showing target is up.
- <a href="https://github.com/omotara100/mitre-attack-threat-mapping/blob/main/screenshots/firewall-icmp.PNG"> firewall-icmp.png</a> — Windows Firewall log snippet showing ICMP-related traffic.
 
----

## Detection Ideas
- Alert on repeated ICMP Echo Requests from a single internal source.
- Monitor firewall logs for spikes in ICMP traffic over short time windows.
- Correlate Nmap-style host discovery with subsequent port scans (T1046).
- SIEM rule: ICMP traffic from non-admin workstations to multiple internal hosts.

