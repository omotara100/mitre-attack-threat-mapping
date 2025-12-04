
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
```bash
nmap -A 192.168.56.101


