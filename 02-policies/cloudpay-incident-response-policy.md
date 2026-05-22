# CloudPay — Incident Response Policy

**Version:** 1.0  
**Owner:** Security Operations  
**Mapped to:** NIST CSF Respond Function · SOC2 CC7.3

---

## 1. Purpose
Define how CloudPay detects, contains, and recovers 
from security incidents to minimise business impact.

---

## 2. Incident Classification

| Severity | Definition | Example | Response Time |
|---|---|---|---|
| P1 Critical | Active breach or data loss | Ransomware, data exfiltration | 15 minutes |
| P2 High | Confirmed attack in progress | Privilege escalation, C2 beacon | 1 hour |
| P3 Medium | Suspicious activity detected | Failed logins, port scan | 4 hours |
| P4 Low | Policy violation or anomaly | Unusual login time | 24 hours |

---

## 3. Incident Response Phases

### Phase 1 — Detection
- SIEM alert fires (ELK Stack / Splunk)
- SOC L1 analyst triages alert
- Relevant Windows Event IDs checked:
  - 4625 — Failed logon
  - 4672 — Privileged logon
  - 4688 — Process creation

### Phase 2 — Containment
- Isolate affected endpoint
- Block malicious IP at firewall
- Preserve logs and memory for forensics

### Phase 3 — Eradication
- Remove malware or threat actor access
- Patch exploited vulnerability
- Reset compromised credentials

### Phase 4 — Recovery
- Restore from clean backup if needed
- Re-enable systems after verification
- Monitor closely for 48 hours post-incident

### Phase 5 — Lessons Learned
- Document timeline of events
- Identify detection gap
- Update SIEM rules to catch it next time

---

## 4. SOC Analyst Responsibilities

| Role | Responsibility |
|---|---|
| L1 Analyst | Triage alerts, initial classification, escalate P1/P2 |
| L2 Analyst | Deep investigation, containment, MITRE ATT&CK mapping |
| IR Lead | Coordinate response, stakeholder communication |

---

## 5. MITRE ATT&CK Mapping

| Technique | ID | Detection Method |
|---|---|---|
| Brute Force | T1110 | Event ID 4625 — repeated failed logons |
| Privilege Escalation | T1068 | Event ID 4672 — special privileges assigned |
| C2 via DNS | T1071.004 | Wireshark — unusual DNS query volume |
| Data Exfiltration | T1041 | NetFlow — large outbound transfer |
