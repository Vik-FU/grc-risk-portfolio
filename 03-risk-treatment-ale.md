# Risk Treatment & Quantitative Loss Modelling

Source: FinSecure Australia Disaster Recovery & Business Continuity Plan (Flinders University, Mar–Jul 2024), aligned to **NIST SP 800-34** contingency planning guidance.

## Business Impact Analysis summary

A Business Impact Analysis was conducted across 7 core business processes, quantifying financial, operational, regulatory, and reputational impact to justify recovery targets:

- **RTO (Recovery Time Objective): 4 hours** for transaction processing
- **RPO (Recovery Point Objective): 1 hour** for transaction processing

Critical asset dependencies (data centres, servers, networks) were mapped to business processes to identify single points of failure ahead of remediation prioritisation.

## Quantitative loss modelling (ALE)

Annualised Loss Expectancy (ALE) = Single Loss Expectancy (SLE) × Annualised Rate of Occurrence (ARO)

| Risk | SLE (Single Loss Expectancy) | ARO (est. occurrences/year) | ALE | Treatment Decision |
|---|---|---|---|---|
| Ransomware on transaction processing | $850,000 (downtime + recovery + regulatory exposure) | 0.15 | $127,500 | **Mitigate** — EDR + tested backup/restore, MFA on admin accounts |
| Untested failover, primary DC outage | $600,000 (outage + SLA penalties) | 0.10 | $60,000 | **Mitigate** — quarterly failover drills |
| Privileged account compromise (no MFA) | $500,000 | 0.20 | $100,000 | **Mitigate** — MFA rollout, priority action |
| Third-party/vendor access incident | $200,000 | 0.25 | $50,000 | **Transfer** — contractual liability clauses + cyber insurance; **Mitigate** via periodic access review |
| Phishing-driven data exposure | $150,000 | 0.30 | $45,000 | **Mitigate** — quarterly phishing simulations, reduce awareness-training-only reliance |
| Classification scheme gaps (low residual) | $80,000 | 0.20 | $16,000 | **Accept** — remediate in normal policy review cycle, not urgent |

## Resulting mitigation budget

The BIA and risk register scored **14 organisational risks by likelihood × impact** (cyberattack risk rated 72/100 — High), driving a **$420,000 risk mitigation budget across 5 categories**:

1. Backup & recovery testing infrastructure
2. Privileged access management / MFA rollout
3. Failover testing and DR exercises
4. Vendor risk review process (contractual + technical)
5. Security awareness program uplift (beyond annual training)

## Treatment decision framework

- **Mitigate** — apply when ALE exceeds the cost of a reasonably available control and the control materially reduces likelihood or impact
- **Accept** — apply when residual risk is low and the cost of further control exceeds the reduction in ALE
- **Transfer** — apply for third-party/vendor exposure where contractual and insurance mechanisms shift financial impact
- **Avoid** — reserved for risks where the underlying activity itself could be discontinued (not used in this register — no findings warranted it)

The finished BIA and risk register were delivered as a client-ready report and presentation, translating technical risk findings into business-facing recommendations.
