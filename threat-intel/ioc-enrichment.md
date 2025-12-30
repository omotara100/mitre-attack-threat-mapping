# IOC Enrichment Workflow

## Objective
To enrich indicators of compromise (IOCs) collected during the phishing incident investigation using publicly available threat intelligence sources.

---

## Indicators Reviewed
- Malicious URL: hxxps://secure-reset[.]co/login
- Domain: secure-reset[.]co
- Sender IP: 185.199.110.153

---

## VirusTotal Enrichment
**Purpose:** Identify known malicious activity associated with URLs, domains, or IPs.

### Workflow
1. Submit the URL, domain, or IP to VirusTotal.
2. Review detection ratios across multiple security vendors.
3. Analyze community comments and historical detections.
4. Note first-seen and last-seen timestamps.

### Expected Outcome
- Confirmation of malicious reputation
- Insight into campaign scope and reuse

---

## AbuseIPDB Check
**Purpose:** Assess whether the sender IP has a history of abusive activity.

### Workflow
1. Submit the sender IP to AbuseIPDB.
2. Review abuse confidence score.
3. Identify reported categories (phishing, spam, brute force).
4. Note reporting frequency and recency.

### Expected Outcome
- Determine likelihood of malicious infrastructure reuse

---

## WHOIS Lookup
**Purpose:** Identify domain ownership and registration patterns.

### Workflow
1. Perform a WHOIS lookup on the suspicious domain.
2. Review domain creation date.
3. Identify registrar and privacy protection usage.
4. Compare domain age against phishing timelines.

### Expected Outcome
- Newly registered domains indicate higher phishing risk

---

## Risk Scoring Concept
A qualitative risk score is assigned based on enrichment findings.

| Factor | Risk Indicator |
|-----|-----|
| Multiple vendor detections | High |
| Newly registered domain | High |
| IP reported for phishing | Medium |
| No detections | Low |

### Overall Risk Assessment
**Risk Level:** High  
**Rationale:** Newly registered domain with phishing indicators and suspicious sender infrastructure.

---

## Analyst Notes
- Indicators are defanged for safety.
- No direct interaction with malicious infrastructure was performed.
- Enrichment findings support phishing classification.

