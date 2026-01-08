# T1049 – System Network Connections

## Overview
This lab demonstrates MITRE ATT&CK Technique **T1049 – System Network Connections**, where an adversary attempts direct network connections to identify reachable services on a remote system.

I used Kali Linux to manually initiate a TCP connection to my Windows 10 machine (192.168.56.101).

---

## What I Did
From the Kali VM, I attempted a direct TCP connection to port 80 on the Windows host to test service availability.

- Manual connection attempt (no scanning)
- Targeted a common web service port
- Observed host response behavior

Target: **192.168.56.101 (Windows)**

---

## Commands Used

nc -nv 192.168.56.101 80
---

## Result Observed
(UNKNOWN) [192.168.56.101] 80 (http) : Connection refused

This indicates:

- The host is reachable
- Port 80 is closed
- The system actively rejected the connection
---

## Evidence Collected

- Kali terminal output showing a refused TCP connection
- No firewall DROP logs observed (connection refused by OS before firewall logging)
- No Sysmon Event ID 3 observed (inbound refused connection not logged by Sysmon)
- This behavior is expected and still demonstrates system network connection discovery.
---

## Detection Ideas

- Monitor repeated TCP connection attempts to closed ports from a single internal host
- Correlate refused connection attempts with earlier scanning activity (T1046)
- Alert when unusual tools (nc, nmap, powershell) attempt direct network connections
- SIEM rule: multiple connection attempts to different ports within a short time window
