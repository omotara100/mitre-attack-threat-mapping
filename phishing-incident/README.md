# 🎣 Phishing Incident Response

## 📌 Overview
This directory contains a **simulated phishing incident investigation** conducted as part of **Week 2** of the *MITRE ATT&CK Threat Mapping* project.

The goal of this exercise is to demonstrate **practical incident response skills**, following the **Detection & Analysis** guidance of **NIST SP 800-61 Rev. 3**, while mapping adversary behavior to the **MITRE ATT&CK framework**.

---

## 🎯 Objectives
This phishing incident response exercise demonstrates the ability to:

- Identify and validate a phishing alert
- Analyze suspicious email indicators
- Assess incident severity and impact
- Collect and document evidence and IOCs
- Map attacker techniques to MITRE ATT&CK
- Maintain clear and professional incident documentation

---

## 🧠 Frameworks & Standards
- **NIST SP 800-61 Rev. 3** – Computer Security Incident Handling Guide  
- **MITRE ATT&CK (Enterprise)**  
- SOC incident response best practices

---

## 🎣 Incident Response Alignment
This phishing incident investigation follows the **Detection and Analysis** guidance outlined in **NIST SP 800-61 Rev. 3**, applying structured SOC workflows for:

- Incident identification  
- Incident analysis  
- Evidence and IOC handling  
- Documentation and reporting  

---

## 🗂️ Contents

---

## 📄 detection.md
Covers the **initial identification of the phishing incident**, including:

- Description of the suspicious email
- Indicators of phishing (spoofed sender, malicious links, urgency)
- Reasoning for classifying the email as malicious

---

## 📄 analysis.md
Documents the **incident analysis phase**, including:

- Incident category and severity
- Potential impact to the organization
- Scope assessment (affected users or accounts)
- **MITRE ATT&CK technique mapping**

### Example Techniques
- **T1566.001** – Phishing: Spearphishing Attachment  
- **T1204.002** – User Execution: Malicious Link  

---

## 📄 evidence.md
Contains **evidence and Indicators of Compromise (IOCs)** collected during the investigation:

- Sender IP addresses
- Malicious domains or URLs
- File hashes (simulated where appropriate)
- Timestamps and affected user details

Evidence is documented to support **incident tracking, escalation, and future detection efforts**.

---

## 🧭 Incident Response Flow
This investigation aligns with the incident handling lifecycle defined in **NIST SP 800-61 Rev. 3** and follows a SOC-style workflow:

1. Alert or User Report  
2. Incident Detection  
3. Incident Analysis  
4. Evidence and IOC Collection  
5. MITRE ATT&CK Technique Mapping  
6. Incident Documentation and Reporting  

---

## 🔗 Relationship to the Overall Project
- **Week 1:** Incident Response foundations and MITRE ATT&CK overview  
- **Week 2:** Phishing Incident Response *(this folder)*  
- **Week 3 (Next):** Endpoint telemetry, Sysmon, and SIEM-based analysis  

This folder provides the **case study foundation** used later for:
- Detection engineering  
- SIEM correlation  
- SOAR automation  

---

## ✅ Skills Demonstrated
- Phishing investigation
- Incident triage and analysis
- Evidence handling and documentation
- MITRE ATT&CK threat mapping
- SOC-style reporting

---

## ⚠️ Disclaimer
This investigation is based on a **simulated phishing incident** and follows guidance from **NIST SP 800-61 Rev. 3**.  
Indicators, logs, and artifacts may be anonymized or fictional for educational and portfolio purposes.

