# Framework Reference

Reusable reference material used across this portfolio.

## Risk rating scale (5×5 likelihood-impact matrix)

| Score | Likelihood | Impact |
|---|---|---|
| 1 | Rare — unlikely to occur | Negligible — no material effect |
| 2 | Unlikely — could occur occasionally | Minor — limited, easily absorbed |
| 3 | Possible — could occur at some point | Moderate — noticeable operational/financial effect |
| 4 | Likely — will probably occur | Major — significant financial, operational, or regulatory effect |
| 5 | Almost certain — expected to occur | Severe — critical, potentially existential |

Inherent Risk = Likelihood × Impact. Bands: 1–6 Low, 8–12 Medium, 15–25 High.

## STRIDE definitions

| Category | Definition |
|---|---|
| **S**poofing | Impersonating something or someone else |
| **T**ampering | Modifying data or code without authorisation |
| **R**epudiation | Denying an action without the ability to prove otherwise |
| **I**nformation Disclosure | Exposing information to unauthorised parties |
| **D**enial of Service | Degrading or denying availability of a system or service |
| **E**levation of Privilege | Gaining capabilities without proper authorisation |

## ISO/IEC 27001:2022 structure (as applied)

- **Clauses 4–10** — management system requirements (context, leadership, planning, support, operation, evaluation, improvement)
- **Annex A** — 93 controls across 4 themes: Organisational (37), People (8), Physical (14), Technological (34)
- A full Statement of Applicability extract covering all 93 controls is in [05-statement-of-applicability-extract.md](05-statement-of-applicability-extract.md)

## NIST CSF 2.0 function map

| Function | Focus |
|---|---|
| **Govern (GV)** | Organisational context, risk strategy, oversight, supply chain |
| **Identify (ID)** | Asset management, risk assessment, improvement |
| **Protect (PR)** | Access control, awareness/training, data security, platform security |
| **Detect (DE)** | Continuous monitoring, adverse event analysis |
| **Respond (RS)** | Incident management, mitigation, communication |
| **Recover (RC)** | Incident recovery planning, restoration, communication |

## ASD Essential Eight (maturity levels 0–3)

Application control · Patch applications · Configure Microsoft Office macro settings · User application hardening · Restrict administrative privileges · Patch operating systems · Multi-factor authentication · Regular backups.

Used in this portfolio to cross-check overlap with ISO 27001 Annex A and NIST CSF — e.g., "Restrict administrative privileges" + MFA map directly to A.8.5 and PR.AA, letting one control implementation satisfy three frameworks simultaneously rather than being tracked and audited separately.
