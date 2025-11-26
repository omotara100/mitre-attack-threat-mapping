MITRE ATT&CK Techniques (42 Total)

This table includes a simple explanation, real example, mitigation, and detection for each technique.

---

## Initial Access (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Phishing (T1566)** | Trick user to click malicious link/file | Fake delivery email installs malware | Email filtering, user training, block macros | Unusual attachments, PowerShell from Word |
| **Exploit Public-Facing App (T1190)** | Break into vulnerable website/server | Outdated web server hacked | Patch systems, use WAF | Strange URLs, spikes in web errors |
| **Valid Accounts (T1078)** | Use stolen credentials | Attacker logs in via VPN | MFA, disable old accounts | Logins from new countries, odd hours |

---

## Execution (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **PowerShell (T1059.001)** | Run malicious commands | Base64-encoded PS commands | Limit PS to admins | PS spawning EXE files |
| **Command Prompt (T1059.003)** | Use cmd.exe to run tools | `net user hacker /add` | Restrict cmd.exe, allow-listing | Office apps spawning cmd |
| **User Execution (T1204)** | User runs malware manually | Fake PDF that installs malware | Block unknown apps | Executing from Downloads |

---

## Persistence (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Startup Folder (T1547.001)** | Program runs every reboot | Malware placed in Startup | Block write access | New file in Startup folder |
| **Scheduled Tasks (T1053)** | Auto-run malware on schedule | Task runs hourly | Restrict task creation | New tasks created |
| **Registry Run Keys (T1547.001)** | Auto-start from registry | Run key loads malware | Lock registry | Registry changes |

---

## Privilege Escalation (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Exploit Vulnerabilities (T1068)** | Use flaws to get admin | Zero-day grants SYSTEM | Patch systems | Token/privilege changes |
| **Bypass UAC (T1548)** | Avoid admin prompts | Malware installs silently | Highest UAC level | Unexpected admin processes |
| **Create Admin Accounts (T1136)** | Make hidden admin user | `net user backdoor /add` | Restrict account creation | New admin accounts |

---

## Defense Evasion (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Obfuscated Commands (T1027)** | Hide malicious code | Base64 PS commands | Block encoded commands | Long Base64 strings |
| **Disable Security Tools (T1562)** | Turn off AV/EDR | Disable Defender real-time | Tamper protection | Security tools disabled |
| **Clear Logs (T1070)** | Delete evidence | `wevtutil cl Security` | Protect logs, send to SIEM | Log deletion, missing logs |

---

## Credential Access (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Keylogging (T1056.001)** | Capture keystrokes | Stealing typed passwords | EDR | Keyboard hook alerts |
| **Credential Dumping (T1003)** | Steal passwords from memory | Mimikatz on LSASS | LSASS protection | LSASS access attempts |
| **Steal Browser Passwords (T1555)** | Read saved passwords | Dump Chrome Login Data | Disable password save | File access to browser data |

---

## Discovery (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Network Scanning (T1046)** | Look for systems | nmap scan | Network segmentation | Port scanning alerts |
| **Enumerate Users (T1087)** | List user accounts | `net user /domain` | Restrict queries | Unusual user enumeration |
| **File Discovery (T1083)** | Search for files | "Where is finance.xlsx?" | Access control | Massive file listing |

---

## Lateral Movement (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **RDP (T1021.001)** | Move to another PC | RDP login with stolen creds | Disable RDP, MFA | Strange RDP activity |
| **Pass the Hash (T1550.002)** | Use password hash | NTLM hash authentication | Credential Guard | NTLM logins from odd devices |
| **SMB Admin Shares (T1021.002)** | Copy tools to \C$ | Pushing malware via SMB | Limit admin shares | Unexpected SMB transfers |

---

## Collection (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Screen Capture (T1113)** | Take screenshots | Steal sensitive screen data | EDR | Screen buffer access |
| **Keylogging (T1056)** | Capture typed data | Password keystrokes | EDR | Keyboard hook alerts |
| **Clipboard Data (T1115)** | Read copied passwords | Read clipboard contents | Disable sharing | Clipboard API access |

---

## Command and Control (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Web Traffic (T1071)** | C2 via web | Beacon every 60 sec | Block domains | Repetitive outbound traffic |
| **Encrypted Channels (T1573)** | Hide C2 in HTTPS | Encrypted malware traffic | TLS inspection | Unknown encrypted traffic |
| **DNS Tunneling (T1071.004)** | Use DNS for C2 | Large DNS queries | DNS filtering | Huge DNS requests |

---

## Exfiltration (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Exfiltration Over Web (T1041)** | Upload files out | Upload to Dropbox | Block sites, DLP | Large POST requests |
| **Email Exfiltration (T1048)** | Send data by email | Data emailed out | Block external send | Large attachments |
| **Exfil Over C2 Channel (T1041)** | Send files to C2 | Malware uploads ZIP | EDR | Big C2 traffic |

---

## Impact (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Ransomware (T1486)** | Encrypt files | Files locked for ransom | Backups | Files rapidly renamed |
| **Data Destruction (T1485)** | Delete files | Mass delete attack | Backup protection | Mass file deletion |
| **Service Stop (T1489)** | Stop security tools | Stop AV service | Protect services | Service stop commands |

---

## Resource Development (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Buy Domains (T1583.001)** | Register phishing sites | Fake login domain | Domain monitoring | Not applicable internally |
| **Create Malware (T1587.001)** | Build hacking tools | Custom RAT created | Threat intel | Not detectable until used |
| **Buy Infrastructure (T1583)** | Buy VPS/servers | Rent server for attacks | Threat intel | Not applicable internally |

---

## Reconnaissance (3)

| Technique | Simple Explanation | Example | Mitigation | Detection |
|----------|--------------------|---------|------------|-----------|
| **Email Harvesting (T1598)** | Find company emails | From website/LinkedIn | Remove public emails | Not internal |
| **Social Media Research (T1593)** | Check employee info | Look at LinkedIn roles | Limit info online | Not internal |
| **Internet Scanning (T1595)** | Scan public systems | Check open ports | Patch & reduce exposure | Not internal |
