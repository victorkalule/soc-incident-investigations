# Case Study 02: PowerShell, Privilege Abuse, and Email Rule Tampering

**Environment:** Authorized cybersecurity training dataset  
**Primary tool:** Splunk Enterprise Security  
**Evidence sources:** Sysmon, PowerShell, osquery, network telemetry, Microsoft 365 / Exchange audit logs  
**Disposition:** True Positive  
**Severity:** High

## Investigation objective

Correlate suspicious events across Windows endpoints, Linux infrastructure, and cloud email services to assess whether the observed behavior constituted an active multi-stage intrusion.

## Findings

The training evidence supported these connected behaviors:

1. **Suspicious PowerShell and network activity:** Several Windows endpoints showed outbound communications associated with command-and-control activity, alongside script-based execution.
2. **Unauthorized account manipulation:** A local account was created and added to an administrative group on a Windows endpoint.
3. **Payload delivery and Linux activity:** Suspicious files were written to a Linux server, with indicators of privilege escalation and attempted evidence removal.
4. **Email configuration abuse:** A Microsoft 365 / Exchange transport rule was created to blind-copy organizational messages to an external destination.
5. **Confidentiality risk:** Suspicious access and transfer activity raised concern about potential exfiltration. The reviewed evidence did **not** establish confirmed completed data exfiltration.

The resulting triage disposition was a **True Positive**, with **High** severity due to compromised systems, unauthorized privilege changes, and email forwarding abuse.

## Relevant MITRE ATT&CK techniques

| Technique | Investigation context |
| --- | --- |
| T1059.001 — PowerShell | Script execution and suspicious commands |
| T1105 — Ingress Tool Transfer | Remote delivery of suspicious files |
| T1136.001 — Create Account: Local Account | Unauthorized local account creation |
| T1098 — Account Manipulation | Changes to account permissions |
| T1114.003 — Email Collection: Email Forwarding Rule | Unauthorized Exchange rule |
| T1071.001 — Application Layer Protocol: Web Protocols | HTTP/HTTPS communications |
| T1070.003 — Indicator Removal on Host: Clear Command History | Attempted deletion of shell history |

## Response recommendations

- Isolate affected endpoints and investigate the Linux server.
- Disable unauthorized accounts and review privileged access.
- Remove and audit unauthorized mail-flow and forwarding rules.
- Preserve endpoint, cloud, and network evidence before remediation.
- Investigate suspicious PowerShell use, command-and-control destinations, and transferred files.
- Strengthen alerts for encoded PowerShell, privilege changes, Linux temporary-directory activity, and Exchange transport-rule changes.

## Analyst learning

This case demonstrated why a SOC investigation should correlate **endpoint, server, identity, and cloud audit data** rather than treating individual alerts independently. It also reinforced the difference between observed exfiltration risk and confirmed data loss.

## Data handling

This is an original portfolio summary of a training case. Account names, addresses, passwords, exact indicators, and raw source logs are intentionally omitted.
