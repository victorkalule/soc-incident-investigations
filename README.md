# SOC Incident Investigations | Splunk & Suricata

**Project type:** Cybersecurity training investigations using historical/simulated datasets  
**Focus:** Security alert triage, SIEM investigation, incident analysis, evidence correlation, and response recommendations

## Overview

This portfolio project documents two investigations I performed during my cybersecurity analyst training. I analyzed security telemetry, assessed alert validity and severity, reconstructed attack timelines, mapped observed behavior to the MITRE ATT&CK framework, and recommended containment, recovery, and detection improvements.

**These are training cases, not production incidents I handled as an employed SOC analyst.** Dates in the case studies refer to activity in the training datasets, not dates of live incidents I personally responded to.

## Tools and techniques

- **SIEM:** Splunk / Splunk Enterprise Security
- **Intrusion detection:** Suricata IDS
- **Log sources:** Windows and Linux telemetry, Sysmon, PowerShell, osquery, network logs, Microsoft 365 / Exchange audit events
- **Framework:** MITRE ATT&CK
- **Workflow:** Alert triage → correlation → timeline → severity and scope assessment → incident reporting → containment and detection recommendations

## Investigations

| Case | Focus | Triage outcome | Selected findings |
| --- | --- | --- | --- |
| [01 — Web compromise and ransomware](cases/01-web-compromise-ransomware.md) | Suricata alert reviewed with Splunk evidence | **True Positive / Critical** | Web scanning and brute force; compromised Joomla site; malicious script execution; Cerber ransomware affecting a workstation and file share |
| [02 — PowerShell, identity abuse, and email rule tampering](cases/02-powershell-identity-email.md) | Splunk Enterprise Security correlation across endpoints, Linux, and Microsoft 365 | **True Positive / High** | Suspicious PowerShell and C2 activity; unauthorized privileged account; Linux privilege escalation; malicious Exchange transport rule |

## My analytical approach

1. Reviewed the detection source and initial alert context.
2. Correlated related events across available log sources and affected assets.
3. Built a timestamped timeline to identify likely attack stages and scope.
4. Evaluated evidence to assign a disposition and incident severity.
5. Mapped observed techniques to MITRE ATT&CK identifiers.
6. Documented containment, remediation, and SOC detection recommendations.

## Selected ATT&CK mappings

- **T1190:** Exploit Public-Facing Application
- **T1110:** Brute Force
- **T1059 / T1059.001:** Command and Scripting Interpreter / PowerShell
- **T1105:** Ingress Tool Transfer
- **T1486:** Data Encrypted for Impact
- **T1136.001:** Create Account: Local Account
- **T1114.003:** Email Collection: Email Forwarding Rule
- **T1070.003:** Indicator Removal on Host: Clear Command History

The mappings reflect the reports' findings and are described in context in the case studies.

## What this project demonstrates

- Distinguishing confirmed malicious activity from unverified assumptions
- Prioritizing incidents using technical evidence and business impact
- Writing clear investigation reports and actionable response recommendations
- Recognizing how endpoint, web, identity, and cloud events connect in multi-stage attacks

## Evidence and publication notes

The source reports contain dataset-specific identifiers, account information, and incident artifacts. To avoid disclosing sensitive or training-restricted material, this repository uses **original summary write-ups** rather than copies of the full reports or raw logs. I will add sanitized screenshots or recreated visualizations only after confirming publication rights.

No live client data, passwords, malware samples, exploit payloads, or private logs are included.

---

*Completed as part of cybersecurity analyst training. Historical timestamps appearing in the investigation materials belong to the case datasets.*
