# DPDPA 2023 — Digital Personal Data Protection Act
# Compliance Checklist

**Company:** CloudPay  
**Prepared by:** Karthikeyan  
**Date:** May 2026  
**Regulation:** Digital Personal Data Protection Act, India 2023

---

## What is DPDPA 2023?

India's first comprehensive data protection law. Enforced by the 
Data Protection Board of India. Applies to any organisation that 
processes digital personal data of Indian citizens — including 
payment platforms like CloudPay.

**Non-compliance penalty:** Up to ₹250 crore per breach.

---

## Key Definitions

| Term | Meaning |
|---|---|
| Data Principal | The individual whose data is collected (the user) |
| Data Fiduciary | The organisation collecting and processing data (CloudPay) |
| Data Processor | Third party processing data on behalf of CloudPay |
| Consent Manager | Registered entity managing user consent |

---

## Section 1 — Lawful Processing and Consent

- [ ] Consent obtained before collecting personal data
- [ ] Consent request written in clear, plain language
- [ ] Consent is specific — not bundled with terms and conditions
- [ ] Users can withdraw consent at any time
- [ ] Consent records maintained with timestamp and version
- [ ] Consent management system implemented or identified

### SOC Analyst Note
> Unauthorised data processing without consent is a breach trigger.
> SOC team monitors access logs to detect unauthorised data queries 
> mapped to MITRE ATT&CK T1530 (Data from Cloud Storage).

---

## Section 2 — Data Principal Rights

| Right | Requirement | CloudPay Status |
|---|---|---|
| Right to access | User can request what data is held | ⬜ Pending |
| Right to correction | User can correct inaccurate data | ⬜ Pending |
| Right to erasure | User can request data deletion | ⬜ Pending |
| Right to grievance | Complaints resolved within 30 days | ⬜ Pending |
| Right to nominate | User can nominate someone to act on their behalf | ⬜ Pending |

---

## Section 3 — Data Fiduciary Obligations

- [ ] Privacy notice published before data collection
- [ ] Purpose of data collection clearly stated
- [ ] Data collected limited to what is necessary (data minimisation)
- [ ] Data not retained beyond the purpose it was collected for
- [ ] Security safeguards implemented to prevent breach
- [ ] Data Protection Officer (DPO) appointed (if significant fiduciary)

---

## Section 4 — Data Breach Notification

- [ ] Breach detection process in place (SIEM alerting)
- [ ] Breach notification to Data Protection Board within 72 hours
- [ ] Breach notification to affected Data Principals documented
- [ ] Breach log maintained with timeline, scope, and actions taken
- [ ] Post-breach review process defined

### SOC Analyst Note
> The SOC team is the first line of defence for breach detection.
> SIEM rules mapped to data exfiltration (T1041) and 
> cloud storage access (T1530) directly support DPDPA breach 
> notification obligations.

---

## Section 5 — Cross-Border Data Transfer

- [ ] Countries receiving Indian personal data identified
- [ ] Transfer only to countries approved by Indian government
- [ ] Contractual safeguards in place with receiving entities
- [ ] Transfer log maintained

---

## Section 6 — Children's Data

- [ ] Age verification mechanism implemented
- [ ] Parental consent obtained for users under 18
- [ ] No behavioural tracking of children's data
- [ ] No targeted advertising directed at children

---

## DPDPA vs SOC2 vs NIST CSF — Quick Mapping

| Requirement | DPDPA 2023 | SOC2 | NIST CSF |
|---|---|---|---|
| Breach notification | Section 8 | CC7.3 | Respond — RS.CO |
| Data minimisation | Section 6 | Confidentiality C1 | Protect — PR.DS |
| Access controls | Section 8 | CC6 | Protect — PR.AC |
| Consent management | Section 6 | Privacy P1 | Govern — GV.PO |
| Vendor risk | Section 8 | CC9 | Identify — ID.SC |
