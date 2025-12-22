
# T1046 – Network Service Discovery (Nmap Scan)

## Overview
This lab demonstrates MITRE ATT&CK Technique **T1046 – Network Service Discovery**, where an adversary performs a network scan to identify open ports and services.  
I used Kali Linux to run an Nmap aggressive scan against my Windows 10 machine (192.168.56.101).

---

## What I Did
From the Kali VM, I executed an aggressive Nmap scan to enumerate:

- Open ports  
- Running services  
- OS and version fingerprinting  
- SMB, RPC, and NetBIOS information  

Target: **192.168.56.101** (Windows)

---

## Firewall Log Evidence Did
The Windows Firewall logs confirm that Nmap probed several common Windows service ports.  
Multiple **DROP** events were recorded for the following ports:

- **Port 139** — SMB NetBIOS Session Service  
- **Port 445** — SMB over TCP  
- **Port 135** — RPC Endpoint Mapper  

These entries match aggressive Nmap scanning behavior (TCP SYN probes).

-----

## Commands Used
nmap -A 192.168.56.101

---

### Screenshots / files
- <a href="https://github.com/omotara100/mitre-attack-threat-mapping/blob/main/screenshots/Kali-nmap.png">  `screenshots/kali-nmap.png`</a>  — Nmap output from Kali.  
- <a href="https://github.com/omotara100/mitre-attack-threat-mapping/blob/main/screenshots/firewall-log.png">  `screenshots/kali-nmap.png`  </a> `screenshots/sysmon-eventid3.png` — Sysmon Event ID 3 showing connection attempts.  
- <a href="https://github.com/omotara100/mitre-attack-threat-mapping/blob/main/screenshots/firewall-log.png">  `screenshots/firewall-nmap-snippet.png`</a>  — filtered firewall log snip (DROP entries).

----

## Detection Ideas
- Alert on bursts of TCP SYNs to multiple destination ports from a single internal source.  
- Create SIEM rule: > X unique destination ports hit by same source within Y seconds (e.g., >20 ports in 10s).  
- Monitor Sysmon Event ID 3 for many distinct DestinationPort values from one SourceIp in a short time window.  
- Create firewall rule alerts for repeated DROP events to well-known service ports (135, 139, 445).
- Suricata/IDS: enable Nmap scan signatures for additional context.

