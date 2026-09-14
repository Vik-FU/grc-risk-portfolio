# Risk Register

Consolidated register combining findings from the FinSecure Australia DR/BCP study and the Protecte Technologies ISMS build. Likelihood and Impact are scored 1–5 (see [04-framework-reference.md](04-framework-reference.md) for the scale); Inherent Risk = Likelihood × Impact.

| ID | Finding | Asset / Process | Likelihood | Impact | Inherent Risk | Existing Control | Residual Risk | ISO 27001 Annex A | NIST CSF 2.0 |
|---|---|---|---|---|---|---|---|---|---|
| R-01 | Ransomware / cyberattack against core transaction processing | Payment processing platform | 4 | 5 | 20 (High) | Perimeter firewall, nightly backups (untested restore) | 12 (Medium) | A.5.30, A.8.13 | RS.MA, RC.RP |
| R-02 | Single point of failure in primary data centre with no tested failover | Data centre / core network | 3 | 5 | 15 (High) | Secondary DC exists, failover not tested | 10 (Medium) | A.5.29, A.8.14 | ID.RA, PR.IR |
| R-03 | No formal Business Impact Analysis prior to this engagement | Enterprise-wide | 4 | 4 | 16 (High) | None | 16 (High) | A.5.29 | ID.IM |
| R-04 | Weak password practices across staff accounts | Identity & access | 4 | 3 | 12 (Medium) | Password policy exists, not enforced technically | 9 (Medium) | A.5.17, A.8.5 | PR.AA |
| R-05 | No multi-factor authentication on privileged accounts | Privileged access | 3 | 5 | 15 (High) | None | 15 (High) | A.8.5 | PR.AA |
| R-06 | Phishing susceptibility among staff | End users | 4 | 3 | 12 (Medium) | Annual awareness training | 8 (Medium) | A.6.3 | PR.AT |
| R-07 | Undocumented third-party/vendor access to internal systems | Vendor management | 3 | 4 | 12 (Medium) | Contracts exist, no access review cadence | 9 (Medium) | A.5.19, A.5.20 | GV.SC |
| R-08 | Cascading failure risk from IoMT device compromise (research finding) | Interconnected healthcare networks (EHR, PACS, IoMT) | 3 | 5 | 15 (High) | Segmentation partial, IDS not AI-driven | 12 (Medium) | A.8.20, A.8.22 | DE.CM |
| R-09 | No incident response runbook for DDoS-triggered cascading outage | Incident response | 3 | 4 | 12 (Medium) | Generic IR policy, no scenario-specific runbook | 10 (Medium) | A.5.24, A.5.26 | RS.MA |
| R-10 | Asset inventory incomplete, dependency mapping not maintained | Enterprise-wide | 3 | 3 | 9 (Medium) | Partial asset register | 6 (Low) | A.5.9 | ID.AM |
| R-11 | Classification scheme not consistently applied to sensitive records | Data governance | 3 | 3 | 9 (Medium) | Classification policy drafted, not rolled out | 6 (Low) | A.5.12, A.5.13 | PR.DS |

**Business translation (sample — R-01):** A successful attack on transaction processing would halt customer-facing payments. Backups exist but restoration has never been tested end-to-end, so the real recovery time is unknown — this is why the DR/BCP work below sets a 4-hour RTO target and treats backup-restore testing as a priority action rather than a "nice to have."

**Business translation (sample — R-05):** Privileged accounts (domain admin, database admin) are the accounts an attacker most wants. Without MFA, a single leaked password is enough to move from a phishing email to full domain compromise — this is treated as a high-residual risk pending an MFA rollout.

See [03-risk-treatment-ale.md](03-risk-treatment-ale.md) for treatment decisions and quantified loss modelling behind the mitigation budget.
