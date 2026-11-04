# SOC Incident Investigations

**Training cases using Splunk, Suricata, and MITRE ATT&CK**

## About this project

I worked through two incident investigations during my cybersecurity analyst training. In both cases, I had to decide whether suspicious activity represented a real threat, work out the sequence of events, and explain what should happen next.

These are investigations of historical training datasets, not incidents I responded to in a production SOC.

## Case 1: Web compromise and ransomware

[Read the case study](cases/01-web-compromise-ransomware.md)

I investigated a critical Suricata alert and used Splunk evidence to follow activity involving a compromised Joomla site, malicious script execution, and Cerber ransomware affecting a workstation and file share.

**Triage result:** True positive — Critical

The main challenge was connecting the activity across systems instead of treating each alert on its own. I documented the affected systems, the evidence supporting the findings, and containment and recovery recommendations.

## Case 2: PowerShell, account abuse, and email rule changes

[Read the case study](cases/02-powershell-identity-email.md)

Using Splunk Enterprise Security and training logs from Windows, Linux, and Microsoft 365, I investigated suspicious PowerShell activity, unauthorized privilege changes, activity on a Linux server, and a malicious Exchange mail-flow rule.

**Triage result:** True positive — High

This case showed me how much context matters when activity appears across different log sources. I also made a distinction between signs of possible data theft and confirmed exfiltration.

## Additional log review — AWS CloudTrail and S3

I also documented a separate [Splunk review of AWS identity activity, S3 bucket permissions, and object access](cases/03-aws-cloudtrail-s3-review.md). This training exercise is an **inconclusive log review**, not a confirmed third incident. The related screenshots are being checked for publication permission and redaction before upload.

## How I approached the investigations

1. Started with the alert and checked the available evidence.
2. Searched related events in Splunk and compared activity across systems.
3. Built a timeline of what happened and which assets were involved.
4. Assessed the severity and documented why the alerts were true positives.
5. Mapped the relevant behavior to MITRE ATT&CK.
6. Wrote recommendations for containment, recovery, and better detection.

## Tools and topics

Splunk, Splunk Enterprise Security, Suricata, PowerShell and Windows events, Linux logs, Microsoft 365 audit events, alert triage, incident timelines, and MITRE ATT&CK.

The ATT&CK techniques discussed in the case studies include **T1190, T1110, T1059.001, T1105, T1486, T1136.001, and T1114.003**.

## What I learned

An initial alert rarely gives the full picture. The useful part of an investigation is showing what the evidence supports, what's still uncertain, and which actions are most important.

The case studies are my own summaries. I haven't included raw logs, training account details, credentials, or malware samples.
