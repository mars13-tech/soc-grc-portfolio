# SOC 2 Type II Audit Readiness Checklist

**Company:** CloudPay  
**Prepared by:** Karthikeyan  
**Date:** May 2026  
**Mapped to:** SOC 2 Trust Service Criteria

---

## Security (CC6) — Logical and Physical Access Controls

### Access Management
- [ ] Access control policy documented and approved
- [ ] MFA enforced for all user accounts
- [ ] MFA enforced for all privileged/admin accounts
- [ ] Quarterly access reviews conducted and documented
- [ ] Terminated employee accounts disabled within 24 hours
- [ ] Principle of least privilege enforced across all systems

### SOC Analyst Note
> Event ID 4625 (failed logon) and 4647 (user-initiated logoff) 
> are key indicators monitored in SIEM to support this criterion.

---

## Security (CC7) — System Operations

### Monitoring and Detection
- [ ] SIEM deployed and actively monitored (ELK Stack / Splunk)
- [ ] Log retention policy defined (minimum 90 days)
- [ ] Alerts configured for critical Event IDs:
  - [ ] 4625 — Failed logon
  - [ ] 4672 — Privileged logon
  - [ ] 4688 — Process creation
  - [ ] 4698 — Scheduled task created
- [ ] Incident response plan documented and tested
- [ ] Security incidents logged and tracked to closure

### SOC Analyst Note
> CC7.3 requires incident response procedures. 
> SOC L1/L2 analysts are the primary owners of this criterion 
> during an audit.

---

## Availability (A1) — System Availability

- [ ] Uptime SLA defined and monitored
- [ ] System availability reports generated monthly
- [ ] Incident response plan covers availability incidents
- [ ] Backup procedures documented
- [ ] Backup restoration tested quarterly
- [ ] Recovery Time Objective (RTO) defined
- [ ] Recovery Point Objective (RPO) defined

---

## Confidentiality (C1) — Confidential Information

- [ ] Data classification policy in place
- [ ] Confidential data identified and labelled
- [ ] Encryption at rest confirmed (AES-256 minimum)
- [ ] Encryption in transit confirmed (TLS 1.2 minimum)
- [ ] Data retention and disposal policy documented

---

## Processing Integrity (PI1)

- [ ] Input validation controls in place
- [ ] Error handling and logging implemented
- [ ] Transaction monitoring active
- [ ] Data accuracy checks documented

---

## Privacy (P1-P8)

- [ ] Privacy notice published and accessible
- [ ] Consent management process documented
- [ ] Data subject rights process defined (access, correction, deletion)
- [ ] Data breach notification process documented (72-hour window)
- [ ] Third-party data processors identified and assessed

---

## Audit Evidence Tracker

| Control | Evidence Location | Owner | Status |
|---|---|---|---|
| MFA enforcement | IAM system screenshot | IT Security | ✅ Complete |
| Access review | Quarterly review spreadsheet | IT Manager | ⬜ Pending |
| SIEM deployment | ELK Stack dashboard screenshot | SOC Team | ✅ Complete |
| IR plan | 02-policies/cloudpay-incident-response-policy.md | Security Lead | ✅ Complete |
| Backup test | Backup restoration log | DevOps | ⬜ Pending |

---

## SOC Analyst Audit Contribution

As a SOC analyst, your direct contribution to a SOC2 audit includes:

1. Providing SIEM alert logs as evidence of monitoring
2. Documenting incident tickets as evidence of CC7.3
3. Showing detection rules as evidence of anomaly monitoring
4. Producing log retention reports as evidence of CC7.2
