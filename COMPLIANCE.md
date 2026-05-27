# How To Configure Blind Insight for Compliance

**An at-a-glance playbook for GDPR, HIPAA, and DORA.**

---

## The Goal

You want to use Blind Insight for analytics and ML while reducing legal and privacy risk.

This guide helps new users:

- Configure a dataset with privacy-by-default controls
- Apply GDPR, HIPAA, and DORA overlays
- Enforce k-anonymity gates before release
- Build an audit-ready evidence package

---

## The Non-Negotiables

### 1) Default-Deny Access

No data access until role + purpose + field scope are explicitly approved.

### 2) Encryption Everywhere

Enable protection at rest, in transit, and in use.

### 3) Separation of Duties

Keep key custodianship separate from data operations and analytics roles.

### 4) Full Auditability

Log user and AI access attempts, policy decisions, key events, and exceptions.

### 5) k-Anonymity Minimums (Mandatory)


| Dataset risk tier | Minimum k required |
| ----------------- | ------------------ |
| **Low risk**      | **k >= 5**         |
| **Moderate risk** | **k >= 10**        |
| **High risk**     | **k >= 20**        |


If minimum k is not met, do not approve release. Apply suppression, generalization, or aggregation, then re-test.

---

## Day 1 Configuration Checklist

Use this in order.

- Build a field-level data inventory (identifiers, quasi-identifiers, sensitive fields)
- Assign risk tier (low/moderate/high)
- Enforce default-deny policy
- Configure least-privilege role/purpose controls
- Enable encryption baseline and key lifecycle controls
- Turn on audit logs + SIEM alerts
- Run k-anonymity assessment and pass threshold for risk tier
- Attach incident triage workflow before go-live
- Select framework overlay(s): GDPR, HIPAA, DORA
- Produce evidence bundle and assign control owners

---

## Framework Overlays

### DORA Overlay

Use for EU financial-sector ICT resilience obligations.

Map controls and evidence to:

- **Arts. 5-9** ICT risk management
- **Arts. 10-14** Incident management
- **Arts. 15-17** Resilience testing
- **Arts. 28-30** Third-party ICT risk
- **Art. 45** Secure information sharing

Prioritize auditor themes: least privilege, data-in-use protection, key separation, full auditability, reduced blast radius.

### GDPR Overlay

Use when personal data is in scope.

Map controls and evidence to:

- **Art. 5(1)(c)** Data minimization
- **Art. 5(1)(f)** Integrity/confidentiality
- **Art. 25** Data protection by design/default
- **Art. 28** Processor obligations
- **Art. 32** Security of processing
- **Art. 33** Breach notification threshold analysis

Always flag residual risks: prompt injection, output leakage, metadata linkage, crypto lifecycle failure.

### HIPAA Overlay

Use when PHI is in scope.

Map controls and evidence to:

- Access control
- Audit controls
- Integrity controls
- Authentication
- Transmission security

Also require organizational controls beyond platform: workforce training, sanctions, contingency planning, BAA governance, document lifecycle.

---

## Fast Decision Rules

### Release Approval

Approve only if:

1. Baseline controls are complete
2. Required overlay controls are complete
3. k-anonymity threshold is met for risk tier
4. Evidence pack is complete and owner-attested

### If k Fails

Do this before release:

1. Suppress or generalize high-risk quasi-identifiers
2. Reduce query granularity and tighten access
3. Restrict outputs to cohort/aggregate reporting where needed
4. Re-run k-anonymity test and document remediation

---

## Evidence Pack (Minimum)

Collect these artifacts for audits and legal review:

- Data inventory and classification manifest
- Access control matrix and approval records
- Encryption and key management configuration records
- Audit log samples and SIEM alert configuration
- k-anonymity assessment report + remediation log
- Incident playbook and breach triage decision tree
- Framework control mapping (GDPR/HIPAA/DORA) with owner sign-off

---

## 30/60/90 Rollout

### Day 0-30

- Complete dataset inventory, access model, encryption, logging
- Assign risk tier and meet k-anonymity threshold

### Day 31-60

- Execute access simulations and incident tabletop
- Validate third-party/transfer checkpoints

### Day 61-90

- Close control gaps
- Finalize compliance narrative and evidence package
- Obtain counsel + governance sign-off for production

---

## Output Template for Users

When users ask for compliance setup, answer in this order:

1. Recommendation
2. Control Mapping
3. Required Evidence
4. Residual Risk and Gaps
5. 30/60/90 Action Plan
6. Counsel Review Flags

---

## Sources

- Blind Insight docs: [https://docs.blindinsight.io](https://docs.blindinsight.io)
- GDPR (EUR-Lex): [https://eur-lex.europa.eu/eli/reg/2016/679/oj](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- EDPB guidelines: [https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines_en](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines_en)
- HIPAA Security Rule (HHS): [https://www.hhs.gov/hipaa/for-professionals/security/laws-regulations/index.html](https://www.hhs.gov/hipaa/for-professionals/security/laws-regulations/index.html)
- HIPAA Breach Notification (HHS): [https://www.hhs.gov/hipaa/for-professionals/breach-notification/index.html](https://www.hhs.gov/hipaa/for-professionals/breach-notification/index.html)
- NIST SP 800-66r2: [https://csrc.nist.gov/pubs/sp/800/66/r2/final](https://csrc.nist.gov/pubs/sp/800/66/r2/final)
- DORA (EUR-Lex): [https://eur-lex.europa.eu/eli/reg/2022/2554/oj](https://eur-lex.europa.eu/eli/reg/2022/2554/oj)
- EIOPA DORA resources: [https://www.eiopa.europa.eu/digital-operational-resilience-act-dora_en](https://www.eiopa.europa.eu/digital-operational-resilience-act-dora_en)

---

## Important Note

This guide supports compliance implementation and documentation. It is not legal advice. Final interpretation and approvals must be made by qualified legal counsel.
