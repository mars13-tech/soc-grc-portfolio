# CloudPay — Vendor Risk Assessment

**Prepared by:** Karthikeyan  
**Date:** May 2026  
**Mapped to:** NIST CSF ID.SC · SOC2 CC9 · DPDPA Section 8

---

## Why Vendor Risk Matters to a SOC Analyst

Third-party vendors are one of the top attack vectors in enterprise 
breaches. The SOC team monitors vendor-related threats including:

- Compromised API keys from third-party integrations
- Supply chain attacks via third-party software updates
- Data exfiltration through vendor access channels

MITRE ATT&CK: T1195 (Supply Chain Compromise), T1199 (Trusted Relationship)

---

## Vendor Risk Scoring Matrix

| Score | Likelihood | Impact | Action |
|---|---|---|---|
| 9–10 | High | Critical | Immediate remediation required |
| 6–8 | Medium | High | Remediation within 30 days |
| 3–5 | Low | Medium | Monitor and review quarterly |
| 1–2 | Low | Low | Accept risk, annual review |

---

## Vendor Risk Register

| Vendor | Service | Data Access Level | Risk Score | Key Risk | Required Control | SOC Monitoring | Review Date |
|---|---|---|---|---|---|---|---|
| AWS | Cloud infrastructure | Critical — all data | 7 | Misconfiguration, data breach | SOC2 report review, CSPM tool, encryption | CloudTrail logs in SIEM | Jun 2026 |
| Stripe | Payment processing | Critical — payment data | 9 | PCI-DSS breach, fraud | PCI-DSS compliance check, tokenisation, contract review | API anomaly alerts in SIEM | Jun 2026 |
| Okta | Identity management | High — all user identities | 8 | Identity breach, MFA bypass | MFA enforcement, access log review, SSO audit | Event ID 4625/4672 monitoring | Jun 2026 |
| Twilio | SMS/OTP delivery | Medium — phone numbers | 5 | SIM swap, OTP interception | Rate limiting, anomaly detection | OTP failure rate alerts | Sep 2026 |
| GitHub | Source code hosting | High — codebase | 7 | Secret exposure, supply chain | Secret scanning enabled, branch protection, 2FA enforced | Repo access log review | Jun 2026 |
| SendGrid | Email delivery | Medium — email addresses | 4 | Phishing misuse, data leak | DKIM/SPF/DMARC configured, volume monitoring | Email gateway alerts | Sep 2026 |
| Datadog | Monitoring/logging | High — log data | 6 | Log data exposure | Data retention limits, access controls, encryption | API key rotation tracking | Jun 2026 |

---

## Vendor Assessment Questionnaire Template

Use this when onboarding a new vendor:

1. Do you have a current SOC2 Type II report? (Y/N)
2. Do you have ISO 27001 certification? (Y/N)
3. How is our data encrypted at rest and in transit?
4. What is your breach notification timeline?
5. Do you conduct annual penetration testing?
6. Who has access to our data within your organisation?
7. Do you subcontract any data processing to fourth parties?
8. What is your data retention and deletion policy?
9. How do you handle our data upon contract termination?
10. Are you compliant with DPDPA 2023 for Indian data?

---

## SOC Monitoring Rules for Vendor Risk

| Vendor | SIEM Alert | MITRE Technique | Action |
|---|---|---|---|
| AWS | Unusual API calls from new IP | T1078 — Valid Accounts | Investigate CloudTrail, check for compromise |
| Stripe | Payment API call volume spike | T1496 — Resource Hijacking | Alert fraud team, rate limit review |
| Okta | Multiple failed SSO attempts | T1110 — Brute Force | Lock account, notify user, escalate to L2 |
| GitHub | New OAuth app authorised | T1195 — Supply Chain | Review app permissions, check for secret exposure |
| All vendors | API key used from new country | T1078 — Valid Accounts | Immediate investigation, possible key rotation |

---

## Quarterly Vendor Review Checklist

- [ ] Collect updated SOC2 reports from critical vendors
- [ ] Review access logs for all vendor integrations
- [ ] Confirm no new subprocessors added without notification
- [ ] Check for any vendor security incidents or breach disclosures
- [ ] Verify encryption standards still meet CloudPay requirements
- [ ] Update risk scores based on new findings
