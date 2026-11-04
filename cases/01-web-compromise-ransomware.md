# Case Study 01: Web Compromise and Ransomware

**Environment:** Authorized cybersecurity training dataset  
**Primary tools:** Suricata IDS and Splunk SIEM  
**Disposition:** True Positive  
**Severity:** Critical

## Investigation objective

Triage a critical Suricata alert and determine whether related activity showed a genuine compromise, how far the incident spread, and which response actions should be prioritized.

## Findings

The case evidence showed multiple malicious activities:

1. **Web intrusion:** Vulnerability scanning and authentication brute-force activity preceded a Joomla web server compromise and website defacement.
2. **Endpoint infection:** An external-media-linked malicious script executed on a workstation and retrieved additional malicious content.
3. **Ransomware impact:** Cerber ransomware executed on the workstation. The training case documented encrypted local files and activity affecting an internal file server over SMB.
4. **Operational impact:** The source investigation documented **401 unique `.txt` files** affected on the workstation and **257 unique `.pdf` files** on the file server.

The initial investigation did **not** establish confirmed data exfiltration.

## Relevant MITRE ATT&CK techniques

| Technique | Investigation context |
| --- | --- |
| T1190 — Exploit Public-Facing Application | Joomla server compromise |
| T1110 — Brute Force | Attempts against web authentication |
| T1059 — Command and Scripting Interpreter | Malicious script execution |
| T1105 — Ingress Tool Transfer | Additional file download |
| T1486 — Data Encrypted for Impact | Ransomware-encrypted files |
| T1021.002 — SMB/Windows Admin Shares | Network file-share involvement |

## Response recommendations

- Isolate the affected workstation and evaluate file-server exposure.
- Preserve relevant logs and artifacts for forensic review.
- Rebuild or restore compromised systems from verified clean sources, following an approved incident response process.
- Review removable-media and script-execution controls.
- Strengthen web application patching, endpoint detection, network segmentation, and backup validation.
- Tune detections for suspicious script launches, unusual SMB behavior, and rapid file modifications.

## Analyst learning

This case reinforced the importance of distinguishing **multiple related attack stages** from a single isolated alert and tying technical events to business impact. It also emphasized precise reporting: ransomware activity was supported by the available records, while exfiltration was not confirmed.

## Data handling

This is an original portfolio summary of a training case. Hostnames, user identifiers, malicious domains, and raw source logs are intentionally omitted.
