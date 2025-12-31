# Phishing Incident Report

## Executive Summary
On April 1, 2025, a phishing email impersonating IT Support was reported by a corporate user. The email attempted to lure the recipient into resetting their password via a malicious link. The incident was investigated, analyzed, and contained with no evidence of user compromise.

---

## Incident Overview
- **Incident Type:** Phishing (Credential Harvesting)
- **Severity:** Medium
- **Status:** Contained
- **Detection Method:** User-reported suspicious email

---

## Timeline of Events
| Time (UTC) | Event |
|----------|------|
| 09:14 | Phishing email received |
| 09:20 | User reported email |
| 09:30 | Initial analysis completed |
| 10:00 | IOCs identified and enriched |
| 10:30 | Detection rule created |

---

## Incident Analysis
The phishing email used urgent language and impersonated IT Support to pressure the user into clicking a malicious link. The sender domain did not match the corporate domain, and the URL led to a credential harvesting page.

No user interaction with the link was confirmed, and no credentials were submitted.

---

## Evidence and Indicators of Compromise (IOCs)
### Email Indicators
- **Sender Email:** it-support@secure-reset[.]co  
- **Sender IP:** 185.199.110.153  
- **Subject:** Urgent: Password Reset Required  

### Network Indicators
- **Malicious URL:** hxxps://secure-reset[.]co/login  
- **Domain:** secure-reset[.]co  

---

## Threat Intelligence Summary
Public threat intelligence sources were used to enrich identified IOCs.

- Newly registered domain
- Infrastructure associated with phishing activity
- Indicators suggest opportunistic credential harvesting

**Overall Risk Assessment:** High

---

## MITRE ATT&CK Mapping
| Tactic | Technique | Description |
|------|---------|------------|
| Initial Access | T1566.002 | Spearphishing Link |
| Execution | T1204.002 | User Execution |

---

## Containment and Response Actions
- Malicious email quarantined
- Indicators shared with detection engineering
- User notified and advised not to interact
- Domain added to blocklist (simulated)

---

## Lessons Learned
- User awareness remains critical for early detection
- Rapid reporting reduces risk of compromise
- Phishing indicators should continuously feed detection logic

---

## Recommendations
- Enhance phishing detection rules
- Conduct regular phishing awareness training
- Implement automated IOC enrichment workflows

---

## Framework Alignment
This incident investigation aligns with the **Detection and Analysis** phase of **NIST SP 800-61 Rev. 3** and demonstrates a structured SOC incident response workflow.

---

## Disclaimer
This incident report is based on a **simulated phishing scenario**. Artifacts and indicators have been anonymized or fictionalized for educational and portfolio purposes.
