# MedCore Clinics Presentation Content

## Slide 1 — Title and Assessment Objective

### On-Slide Content

- MedCore Clinics
- GRC Risk Assessment
- NIST Cybersecurity Framework 2.0
- Design / Pre-Implementation
- Prepared by: [STUDENT NAME]

### Suggested Visual

Use a clean title slide with a small healthcare, cloud, and risk icon set. Keep the design professional and avoid decorative clutter.

### Speaker Notes

This presentation summarizes a design-phase cybersecurity GRC assessment for MedCore Clinics. MedCore is preparing to migrate patient records from 14 local clinic systems into a single cloud-hosted EHR platform called ClinicCloud. The assessment was performed before implementation and before production patient data is migrated. The goal is to identify what could go wrong, map the issues to NIST Cybersecurity Framework 2.0 outcomes, score the risks qualitatively, and recommend what must be fixed before go-live. Because this was originally structured for a six-person team but completed as a solo submission, the work covers the risk analyst, compliance officer, threat modeler, control owner/auditor, policy writer, and presenter responsibilities in one integrated package.

## Slide 2 — MedCore Scenario and Scope

### On-Slide Content

- Fourteen outpatient clinics
- Cloud EHR migration to ClinicCloud
- Regulated patient data
- No formal security function
- Three major third-party relationships
- Helpdesk contractor support model

### Suggested Visual

Use a compact scope map: clinics on the left, ClinicCloud in the center, and billing, reminder, and backup/vendor services on the right.

### Speaker Notes

MedCore operates 14 outpatient clinics across three cities. Historically, each clinic kept records in its own locally installed practice-management application with paper backups. Leadership approved a migration to a single cloud EHR so patient history, scheduling, and billing can be centralized. The major concern is that this change concentrates sensitive patient information in a shared SaaS environment while MedCore has no formal security function, no security policy, no formal access-control process, and no prior risk assessment. The key third-party relationships are ClinicCloud, the billing clearinghouse, and the reminder service, with the IT helpdesk contractor also playing an important operational support role.

## Slide 3 — Architecture and Sensitive Data Flows

### On-Slide Content

- Clinic workstations use browser access
- ClinicCloud web app and primary database
- CSV migration from 14 legacy systems
- Billing and reminder integrations
- Vendor backup storage
- Contractor remote access

### Suggested Visual

Recreate the report architecture diagram as a simple data-flow diagram. Show clinics, public internet, ClinicCloud, primary database, migration folder, billing clearinghouse, reminder service, backup storage, and contractor remote access.

### Speaker Notes

The architecture is a public-internet SaaS model. Existing Windows clinic laptops use Chrome to connect to ClinicCloud over HTTPS. Inside the vendor boundary, the web application connects to application servers and the primary database, which stores patient records, PII, PHI, billing data, and appointments. ClinicCloud also sends claim data to the billing clearinghouse and appointment data to the reminder service. During migration, all 14 legacy systems export records to CSV files, which are uploaded to a shared migration folder and imported by the vendor. Backups are planned nightly to vendor backup storage, but region and encryption status are not specified. The helpdesk contractor will remotely support clinic workstations, but the tool is still undefined.

## Slide 4 — NIST CSF 2.0 Methodology

### On-Slide Content

- Govern
- Identify
- Protect
- Detect
- Respond
- Recover
- 5x5 qualitative risk matrix

### Suggested Visual

Use the six NIST CSF 2.0 functions as a horizontal lifecycle with a small 5x5 heat-map thumbnail beside it.

### Speaker Notes

NIST CSF 2.0 was selected because it is practical and risk-based. MedCore does not have a mature security management system, so the framework needs to support building a program from the design stage rather than auditing an existing program. NIST CSF covers governance, asset identification, protection, detection, response, and recovery, which aligns well with MedCore's cloud migration, regulated patient data, and vendor dependencies. The scoring method is qualitative only. Each risk uses likelihood and impact from 1 to 5, multiplied to produce Low, Medium, High, or Critical levels. The assessment does not calculate financial loss, ALE, or SLE.

## Slide 5 — Critical Assets and Trust Boundaries

### On-Slide Content

- Patient PHI and PII
- Staff credentials
- ClinicCloud primary database
- Legacy CSV exports
- Clinic workstations
- Vendor and contractor boundaries

### Suggested Visual

Use a two-column slide: left side lists critical assets; right side shows trust boundaries around clinic endpoints, public internet, ClinicCloud, migration folder, vendors, and helpdesk contractor.

### Speaker Notes

The most important assets are the patient data and the access paths to that data. Patient PHI includes clinical notes and diagnosis codes. Patient PII includes name, DOB, address, and phone. Staff credentials are especially sensitive because ClinicCloud authentication is currently password-only. The ClinicCloud primary database is mission-critical because it will hold records, appointments, billing, and patient information. Legacy CSV exports are also high risk because they may contain bulk historical patient records from all clinics. The key trust boundaries are clinic endpoints, the public internet, ClinicCloud's SaaS environment, the shared migration folder, external billing and reminder vendors, and the helpdesk contractor's remote-access path.

## Slide 6 — Gap-Analysis Findings

### On-Slide Content

- Not Addressed: 15
- Partially Addressed: 9
- Fully Addressed: 0
- `G-13`: MFA not enabled
- `G-14`: Clinic-level access not designed
- `G-19`/`G-20`: Logs and monitoring missing

### Suggested Visual

Use a stacked bar or three-count summary for gap status, with callout labels for the top five gaps: `G-13`, `G-14`, `G-19`/`G-20`, `G-21`/`G-22`, and `G-10`/`G-11`.

### Speaker Notes

The gap analysis assessed 24 NIST CSF 2.0 outcomes. Fifteen are Not Addressed, nine are Partially Addressed, and none are Fully Addressed based on the current design documentation. The strongest launch blockers are access control, monitoring, incident response, and vendor governance. MFA is available but not enabled. Clinic-level patient access is not designed, so a clinician at any clinic can currently see patients from other clinics. MedCore has no designed access to relevant audit logs and no MedCore-side monitoring. It also has no incident-response plan or breach-notification procedure. Finally, no vendor risk assessments or contract security addenda have been completed for ClinicCloud, the billing clearinghouse, or the reminder service.

## Slide 7 — Top Five Risks

### On-Slide Content

| Risk ID | Short Title | Score | Level |
| --- | --- | ---: | --- |
| `R-01` | Password-only account takeover | 20 | Critical |
| `R-02` | Cross-clinic patient access | 20 | Critical |
| `R-03` | CSV migration-file exposure | 20 | Critical |
| `R-04` | Unmanaged laptop compromise | 16 | Critical |
| `R-05` | Contractor remote-access compromise | 16 | Critical |

### Suggested Visual

Use a compact 5x5 risk heat map. Place `R-01`, `R-02`, and `R-03` in Likelihood 4 / Impact 5; place `R-04` and `R-05` in Likelihood 4 / Impact 4.

### Speaker Notes

The highest-scored risks are concentrated around access, migration, endpoints, and support access. `R-01` is password-only ClinicCloud account takeover, scored 20 Critical because ClinicCloud is internet-accessible and MFA is not enabled. `R-02` is excessive cross-clinic access, also 20 Critical, because the design explicitly allows clinicians to see patients from other clinics. `R-03` is legacy CSV migration-file exposure, 20 Critical, because bulk patient records will be staged in a shared folder without completed retention or handling controls. `R-04` is unmanaged laptop compromise, 16 Critical, because clinic workstations are old and patch status is unknown. `R-05` is contractor remote-access compromise, 16 Critical, because the remote-support tool and controls are not yet defined.

## Slide 8 — Multi-Step Attack Chain

### On-Slide Content

1. Compromised clinic laptop
2. Credential or session theft
3. No MFA
4. ClinicCloud access
5. Excessive cross-clinic permissions
6. Multi-clinic patient-data exposure
7. Delayed detection

### Suggested Visual

Use a left-to-right attack-chain diagram with seven numbered nodes. Add a note under the diagram: "Plausible design-phase scenario, not an actual incident."

### Speaker Notes

This attack chain shows how several design gaps combine into one realistic scenario. It begins with a stolen or compromised clinic laptop. Because patch status is unknown and unmanaged, the device may be easier to compromise or abuse. From there, an attacker steals a clinician password or browser session. MFA is not enabled, so the attacker can access ClinicCloud over the public internet. The current role model then increases impact: a clinician account is not limited by clinic location, so the attacker may access records beyond one clinic. Finally, because MedCore has no designed access to audit logs and no monitoring process, detection and response may be delayed. This is not an actual incident; it is a plausible design-phase risk path.

## Slide 9 — Business Impact and Remediation Roadmap

### On-Slide Content

- Mission-critical: patient records, primary database, recovery
- Highest recovery priority: clinical access
- Before go-live actions are launch blockers
- First 90 days: reviews, tests, training
- Long term: reassessment and continuous governance

### Suggested Visual

Use a three-horizon roadmap with three bands: Before Go-Live, First 90 Days, and Longer-Term. Highlight before-go-live items in the strongest color.

### Speaker Notes

The BIA identified access to clinical patient records, the ClinicCloud primary database, and backup and recovery capability as mission-critical. These processes have the strictest recovery expectations because they directly affect patient care and regulated patient data. The remediation roadmap is divided into three horizons. Before go-live actions are launch blockers: MFA, least privilege, clinic-level access, secure migration handling, endpoint management, vendor assessments and contract terms, audit logs, monitoring, incident response, breach notification, backup validation, and secure remote access. The first 90 days focus on operating the controls: access reviews, offboarding tests, recovery tests, staff training, log reviews, tabletop exercises, and vendor monitoring. Longer-term work turns these into a continuous governance program.

## Slide 10 — Go-Live Recommendation

### On-Slide Content

> No-Go in the Current Design

- Mandatory MFA
- Least privilege and clinic-level access
- Secured migration process
- Managed endpoints
- Verified vendor and backup controls
- Logging, monitoring, and incident readiness

### Suggested Visual

Use a decision slide with a clear "No-Go" status marker and a conditional approval checklist beneath it.

### Speaker Notes

The recommendation is that MedCore should not proceed to production in the current design. Conditional go-live approval should be granted only after all before-go-live remediation actions have been implemented and verified. The required conditions are mandatory MFA, least-privilege access, clinic-level patient restrictions, a secured migration process, centrally managed and patched clinic laptops, verified vendor and backup controls, access to logs, monitoring, an incident-response plan, and breach-notification readiness. The single most important recommendation is to require multi-factor authentication and enforce least-privilege, clinic-level access before any production patient data is migrated. Without those controls, the migration would place regulated patient data into a shared cloud platform before MedCore can adequately protect, monitor, or respond to access misuse.
