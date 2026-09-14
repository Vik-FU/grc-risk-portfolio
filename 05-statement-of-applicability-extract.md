# Statement of Applicability — Extract

Full SoA built from scratch across all 93 ISO/IEC 27001:2022 Annex A controls, defining scope and security objectives before control-level applicability was assessed. This extract shows a representative sample from each of the 4 control themes; the complete SoA covers all 93 controls.

**Scope statement (summary):** All information assets, systems, and processes supporting core service delivery, including staff endpoints, cloud-hosted applications, and third-party integrations. Excludes physical sites outside direct organisational control (covered instead via vendor contractual clauses — see A.5.19–A.5.21 below).

| Control | Title | Theme | Applicable? | Justification | Status |
|---|---|---|---|---|---|
| A.5.1 | Policies for information security | Organisational | Yes | Foundational governance requirement | Implemented |
| A.5.9 | Inventory of information and other associated assets | Organisational | Yes | Required to scope risk assessment accurately | Partially implemented |
| A.5.12 | Classification of information | Organisational | Yes | Sensitive records require differentiated handling | Drafted, not rolled out |
| A.5.17 | Authentication information | Organisational | Yes | Directly addresses password-related risk (R-04) | Implemented |
| A.5.19 | Information security in supplier relationships | Organisational | Yes | Third-party access is an identified risk (R-07) | Partially implemented |
| A.5.24 | Information security incident management planning | Organisational | Yes | No scenario-specific runbook exists yet (R-09) | Gap — planned |
| A.5.30 | ICT readiness for business continuity | Organisational | Yes | Directly supports RTO/RPO targets from the BIA | Implemented |
| A.6.3 | Information security awareness, education and training | People | Yes | Phishing susceptibility identified (R-06) | Implemented, effectiveness under review |
| A.7.2 | Physical entry | Physical | Yes | Data centre access control | Implemented |
| A.7.10 | Storage media | Physical | Yes | Backup media handling | Implemented |
| A.8.5 | Secure authentication | Technological | Yes | MFA gap on privileged accounts (R-05) | Gap — priority remediation |
| A.8.13 | Information backup | Technological | Yes | Backup exists but restore untested (R-01) | Partially implemented |
| A.8.14 | Redundancy of information processing facilities | Technological | Yes | Secondary DC exists, failover untested (R-02) | Partially implemented |
| A.8.16 | Monitoring activities | Technological | Yes | Supports detection function generally | Partially implemented |
| A.8.20 | Networks security | Technological | Yes | Segmentation for IoMT/medical device traffic (R-08) | Partially implemented |
| A.8.22 | Segregation of networks | Technological | Yes | Same rationale as A.8.20 | Partially implemented |

**Note on "not applicable" entries:** in the full 93-control SoA, a small number of controls were marked not applicable with documented justification (e.g., controls specific to physical retail environments, where the in-scope organisation operates entirely from office and cloud environments). Every "not applicable" determination is documented with a rationale, per ISO/IEC 27001 Clause 6.1.3(d) requirements — auditors will test this during certification, so a bare "N/A" without justification is a common finding against organisations.

Cross-reference: see [01-risk-register.md](01-risk-register.md) for how gaps identified here (A.8.5, A.5.24, A.5.19) map to specific residual risks, and [03-risk-treatment-ale.md](03-risk-treatment-ale.md) for the quantified justification behind prioritising the A.8.5 (MFA) remediation.
