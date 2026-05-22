# CloudPay — Security Risk Register

**Last Updated:** May 2026  
**Mapped to:** NIST CSF 2.0 · SOC2 CC3.2

| Risk ID | Risk | Likelihood | Impact | Score | SOC Detection Method | Control | Status |
|---|---|---|---|---|---|---|---|
| R-001 | Unauthorised access to payment data | High | Critical | 9 | Event ID 4625 — failed logons | MFA enforcement | Open |
| R-002 | Malware on endpoint | Medium | Critical | 8 | EDR alert + Event ID 4688 | EDR deployment, patch management | In Progress |
| R-003 | Privilege escalation | Medium | High | 7 | Event ID 4672 | Least privilege policy | Open |
| R-004 | Data exfiltration via DNS | Low | Critical | 7 | Wireshark DNS analysis | DNS filtering, DLP | Monitoring |
| R-005 | Insider threat | Low | High | 6 | UEBA, audit log review | Access reviews, DLP | Monitoring |
| R-006 | Phishing leading to credential theft | High | High | 8 | Email gateway alerts | Security awareness, MFA | Open |
| R-007 | Unpatched third-party dependency | Medium | High | 6 | Vulnerability scanner | Patch management policy | In Progress |
| R-008 | Ransomware via RDP | Low | Critical | 7 | Event ID 4624 — RDP logon | Disable RDP, network segmentation | Open |
| R-009 | C2 beacon over HTTPS | Low | High | 5 | SIEM — traffic anomaly | SSL inspection, threat intel feeds | Monitoring |
| R-010 | Cloud misconfiguration | Medium | High | 6 | CSPM alerts | Cloud security baseline | Open |
