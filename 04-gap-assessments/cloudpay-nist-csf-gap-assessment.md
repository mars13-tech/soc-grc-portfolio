# CloudPay — NIST CSF 2.0 Gap Assessment

**Assessed by:** Karthikeyan  
**Date:** May 2026  
**Framework:** NIST CSF 2.0

| Function | Category | Current State | Target State | Gap | SOC Fix | Priority |
|---|---|---|---|---|---|---|
| Identify | Asset Management | No formal CMDB | Full asset inventory | High | Build asset register | P1 |
| Protect | Access Control | MFA on admin only | MFA on all users | High | Enforce MFA org-wide | P1 |
| Protect | Awareness Training | No formal program | Annual training | Medium | Implement security training | P2 |
| Detect | Log Management | No centralised logs | SIEM in place | Critical | Deploy ELK Stack | P1 |
| Detect | Anomaly Detection | No alerting | Real-time SIEM alerts | Critical | Write detection rules in Splunk/ELK | P1 |
| Respond | IR Plan | No documented plan | Tested IR playbook | High | Implement IR policy | P1 |
| Respond | Communications | No escalation path | Defined escalation matrix | Medium | Define L1→L2→IR Lead path | P2 |
| Recover | Backup | Partial backups | Full tested recovery | Medium | Test backup restoration quarterly | P2 |
| Govern | Policies | Partial | Full policy library | High | Complete policy documentation | P2 |
