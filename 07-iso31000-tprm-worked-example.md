# ISO 31000 Third-Party Risk Assessment — Worked Example

**Illustrative portfolio project. Scenario, organisation names, scores, and dates are fictional, built for demonstration only. Not associated with any real employer.**

This project walks a single Material Service Provider through the full ISO 31000 risk management process end to end — establishing context, risk identification, analysis, evaluation, treatment, and monitoring & review — and shows where each ISO 31000 stage feeds directly into an ISO 27001:2022 clause or Annex A control, so the same risk work satisfies two frameworks at once.

## Scenario

**Assessing organisation:** Meridian Financial Group, an illustrative APRA-regulated ADI, subject to CPS 230, operating an ISO 27001-certified ISMS
**Third party assessed:** CloudVault Data Services, an illustrative Material Service Provider engaged to host and back up core banking data, including disaster recovery services
**Risk appetite:** Low tolerance for risks that could expose customer data or interrupt core banking availability beyond a 4-hour recovery time objective. Risks scoring Extreme cannot be accepted without Board Risk Committee sign-off.

## Risk register (identify → analyse → evaluate → treat)

| ID | Category | Risk | Inherent (L×I) | Inherent Level | Treatment Action | Owner | Residual (L×I) | Residual Level |
|---|---|---|---|---|---|---|---|---|
| R1 | Data Security & Access Control | Unauthorised access to customer data — no MFA enforced, access reviews not evidenced | 3×5=15 | Extreme | Require MFA for all admin access + quarterly access reviews, audited annually | IT Security Lead | 2×5=10 | High |
| R2 | Operational Resilience | Extended outage delaying backup restoration beyond the 4-hour RTO | 2×4=8 | Medium | Renegotiate SLA to contractual 4-hour RTO / 1-hour RPO; require quarterly DR test evidence | Vendor Relationship Manager | 1×4=4 | Low |
| R3 | Fourth-Party / Subcontracting | Undisclosed offshore fourth-party subcontracting of data processing | 4×4=16 | Extreme | Amend contract to require disclosure and prior approval of all subcontractors, with right to assess their security posture | Third-Party Risk Manager | 2×4=8 | Medium |
| R4 | Regulatory & Compliance | No contractual breach-notification timeframe — risks a missed CPS 230 / Privacy Act notification | 2×5=10 | High | Mandate contractual notification within 24 hours of any confirmed or suspected incident | Legal & Contracts | 2×5=10 | High |
| R5 | Business Continuity | CloudVault's DR/BCP has never been tested | 3×4=12 | High | Require an annual, evidenced DR/BCP test, results shared with Meridian's BC Manager | Business Continuity Manager | 2×4=8 | Medium |
| R6 | Contractual / Governance | No right-to-audit clause in the service agreement | 4×2=8 | Medium | Add a right-to-audit clause, exercisable annually or after a material incident | Legal & Contracts | 1×2=2 | Low |

## Inherent vs residual risk

Before treatment: **2 Extreme, 2 High, 2 Medium, 0 Low.**
After treatment: **0 Extreme, 2 High, 2 Medium, 2 Low.**

Both Extreme-rated risks (R1: access control, R3: undisclosed fourth-party) drop out of the Extreme band once treatment actions land — which is the point of scoring inherent and residual risk separately: it shows the Board Risk Committee exactly how much risk reduction each treatment action is expected to deliver, not just a final "acceptable" label.

## Monitoring & KRIs

| KRI | Linked Risk | Target | Current (illustrative) | Trend |
|---|---|---|---|---|
| % of vendor access reviews completed on schedule | R1 | ≥95% | 88% | Improving |
| SLA breaches affecting availability | R2 | 0 per quarter | 1 this quarter | Stable |
| Undisclosed fourth-party subcontractors identified | R3 | 0 | 1 (offshore processor) | Under remediation |
| Contractual breach-notification SLA in place | R4 | Yes, ≤24 hrs | Not yet contracted | Pending contract amendment |
| Evidenced DR/BCP test completed | R5 | Annual | Not yet tested | Scheduled Q1 2027 |

Review cadence: quarterly vendor performance review (Third-Party Risk Manager), annual full ISO 31000 reassessment (Risk Committee), annual Board Risk Committee reporting alongside the Material Service Provider register, plus ad hoc review triggered by a security incident, material contract change, adverse audit finding, or new regulatory guidance.

## ISO 31000 → ISO 27001 crosswalk

ISO 31000 is the generic parent standard for risk management; ISO 27001's own risk process (Clause 6.1.2/6.1.3) is a domain-specific application of the same principles to information security. Each stage of this project also satisfies an ISO 27001 requirement:

| ISO 31000 Stage | What This Project Did | ISO 27001:2022 Clause | Relevant Annex A Controls |
|---|---|---|---|
| Establishing the context | Defined scope, risk appetite, and likelihood/impact criteria for the engagement | Clause 4.1/4.2, 6.1.2(a) | A.5.1 Policies for information security |
| Risk identification | Identified six risks tied to the vendor's role as a Material Service Provider | Clause 6.1.2(c) | A.5.9 Inventory of assets; A.5.19 Information security in supplier relationships |
| Risk analysis & evaluation | Scored each risk and compared it against the risk appetite | Clause 6.1.2(d)/(e) | Feeds the Statement of Applicability (SoA) |
| Risk treatment | Defined a treatment action, owner, and target date for each risk | Clause 6.1.3, 8.3 | A.5.20 Supplier agreements; A.5.21 ICT supply chain; A.5.22 Monitoring supplier services |
| Monitoring & review | Set a quarterly/annual review cadence and five KRIs | Clause 9.1, 9.3 | A.5.35 Independent review; A.5.36 Compliance with policies and standards |
| Recording, reporting & consultation | Reported results to the Risk Committee quarterly and the Board annually | Clause 5.3, 7.4, 9.2 | Supports internal audit evidence trail |

**Why this matters:** one piece of vendor risk work produces evidence an ISO 27001 auditor expects behind Annex A supplier controls *and* the board-level reporting CPS 230 requires directly — the same register serves both frameworks rather than being built twice.

The full workbook (editable risk register, colour-coded heat maps, and a live crosswalk) is available as an Excel file — see [`ISO31000-TPRM-Risk-Assessment.xlsx`](ISO31000-TPRM-Risk-Assessment.xlsx) in this repo.
