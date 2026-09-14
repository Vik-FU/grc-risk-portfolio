# STRIDE Threat Model — Cascading DDoS Failure in Interconnected Healthcare Networks

Source: PRISMA-guided systematic review of 47 peer-reviewed studies (screened from 746 records across Covidence, IEEE Xplore, and PubMed), examining how DDoS attacks propagate across interconnected hospital systems — Electronic Health Records (EHR), Picture Archiving and Communication Systems (PACS), and Internet of Medical Things (IoMT) devices.

Scenario: a botnet of compromised IoMT devices (infusion pumps, patient monitors) is used to launch a volumetric DDoS attack against the hospital network edge, degrading connectivity to EHR and PACS and disrupting telemedicine services.

| STRIDE Category | Applicable? | Attack Vector | Existing Control | Residual Exposure |
|---|---|---|---|---|
| **S**poofing | Yes | Compromised IoMT devices spoofing legitimate network traffic to evade basic ACLs | Network segmentation (partial), device allow-listing | Medium — many IoMT devices lack certificate-based identity |
| **T**ampering | Yes | Firmware tampering on unpatched IoMT devices to recruit them into a botnet | Vendor patch cycles (slow, often 6–12 months) | High — patching cadence lags known CVEs |
| **R**epudiation | Partial | Limited device-level logging makes it hard to attribute which device originated malicious traffic | Centralised SIEM ingesting network logs only (not device logs) | Medium |
| **I**nformation Disclosure | Low (in this scenario) | Not the primary vector, but outage can force fallback to less secure manual/paper processes | Downtime procedures exist but are not security-hardened | Low–Medium |
| **D**enial of Service | Yes (primary) | Volumetric DDoS from IoMT botnet overwhelming network edge, degrading EHR/PACS availability | Perimeter DDoS scrubbing (ISP-level, no on-prem redundancy) | High — extended outages reduce diagnostic capacity and increase patient risk |
| **E**levation of Privilege | Possible secondary effect | During outage-driven fallback procedures, emergency access overrides may bypass normal privilege checks | "Break-glass" access exists, review of break-glass usage is inconsistent | Medium |

## Key finding

The review's synthesis found that the highest-impact exposure isn't the DDoS itself — it's the **absence of AI-driven anomaly detection tuned for medical-device traffic patterns**, combined with slow IoMT patch cycles. Traditional network intrusion detection is tuned for IT traffic, not the periodic, low-bandwidth signatures typical of medical devices, so botnet recruitment activity blends into normal noise until the attack is already underway.

## Proposed resilience framework

1. AI-driven intrusion detection trained specifically on IoMT traffic baselines (not generic IT/OT signatures)
2. NIST CSF–aligned governance for medical device lifecycle management (asset inventory, patch SLAs, decommissioning)
3. Tested operational fallback procedures — not just documented ones — including break-glass access review after every activation

Mapped against NIST CSF 2.0: this framework sits primarily in **Detect (DE.CM)** and **Protect (PR.IR, PR.PS)**, with **Govern (GV.SC)** covering vendor/device supply-chain accountability for patch cadence.

See [01-risk-register.md](01-risk-register.md) (R-08, R-09) for how this maps into the consolidated register.
