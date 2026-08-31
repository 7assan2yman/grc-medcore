# MedCore Clinics Access Control Policy

## Document Control

| Field | Value |
| --- | --- |
| Policy title | MedCore Clinics Access Control Policy |
| Policy owner | Chief Operating Officer, interim recommended owner |
| Version | 1.0 |
| Status | Proposed for adoption before production use |
| Effective date | [EFFECTIVE DATE] |
| Review date | [REVIEW DATE] |
| Approving authority | [APPROVING AUTHORITY] |
| Classification | Academic / Confidential Scenario |

## 1. Purpose

This policy protects MedCore Clinics patient, employee, operational, and authentication information by enforcing consistent access controls. It directly supports the MedCore risk assessment recommendation to require multi-factor authentication and enforce least-privilege, clinic-level access before any production patient data is migrated.

## 2. Scope

This policy applies to MedCore employees, clinicians, front-desk staff, contractors, IT support personnel, temporary personnel, third-party service providers, and any other user or service account with access to MedCore data. It applies to ClinicCloud, clinic workstations, migration resources, third-party integrations, remote-support systems, and any system that processes, stores, transmits, or administers MedCore data.

## 3. Definitions

| Term | Definition |
| --- | --- |
| Authentication | The process of verifying the identity of a user, service, or device. |
| Authorization | The process of granting approved access to specific systems, data, or functions. |
| Least privilege | Access limited to the minimum systems, data, and functions required for an approved business purpose. |
| Minimum necessary | Patient-data access limited to the smallest amount needed to perform an assigned role or task. |
| MFA | Multi-factor authentication using at least two different authentication factors. |
| Privileged account | An account with administrative, configuration, security, migration, integration, or elevated support capabilities. |
| Break-glass access | Emergency access used only when normal access is unavailable and urgent operational or patient-care need exists. |
| Access owner | The manager, clinical director, system owner, or data owner accountable for approving and reviewing access. |
| Contractor access | Access granted to non-MedCore personnel, including helpdesk, vendor, temporary, or support staff. |

## 4. Policy Statements

1. `AC-01` Unique accounts for every user: Every MedCore employee, clinician, front-desk user, contractor, vendor support user, and administrator must use a unique account assigned to one named individual before accessing MedCore systems or data.
2. `AC-02` Shared accounts prohibited: Shared, generic, group, or unmanaged accounts are prohibited for ClinicCloud, migration resources, remote-support tools, third-party integrations, and administrative functions unless approved as a time-limited exception under `AC-20`.
3. `AC-03` MFA mandatory for ClinicCloud: Multi-factor authentication must be enabled and enforced for every ClinicCloud user account before ClinicCloud is used with production patient data.
4. `AC-04` MFA mandatory for remote and privileged access: MFA must be enforced for all remote-support access, privileged accounts, migration-folder access, vendor support access, and administrative access before production use.
5. `AC-05` Least-privilege access: Access permissions must be limited to the minimum systems, records, functions, and administrative capabilities required for approved job duties.
6. `AC-06` Minimum-necessary patient-data access: Access to patient PII, PHI, billing data, appointment data, and legacy migration files must be limited to the minimum necessary for the user's role and assigned work.
7. `AC-07` Clinic-level access restrictions: ClinicCloud access must enforce clinic-level patient-access restrictions so users can access only the patient records authorized for their assigned clinic or formally approved cross-clinic role.
8. `AC-08` Formal access-request approval: New access must require a written request, business justification, access owner approval, role selection, clinic assignment when applicable, and completion evidence before activation.
9. `AC-09` Role-based access assignment: Access must be assigned using approved roles such as Clinician, Front Desk, administrator, migration support, vendor support, or contractor support; direct custom permissions must be approved by the access owner and documented.
10. `AC-10` Account modification after role changes: Managers and access owners must request access changes within 24 hours of a role, clinic, employment-status, or contract-status change.
11. `AC-11` Timely account termination: Accounts for terminated users, departed contractors, expired temporary staff, completed support tasks, and completed vendor migration activities must be disabled within 24 hours or sooner when technically possible.
12. `AC-12` Quarterly access reviews: Access owners must review user, clinic-level, privileged, contractor, migration, vendor, and exception access at least quarterly and document approval, correction, or removal.
13. `AC-13` Privileged-account restrictions: Privileged accounts must be assigned only to named authorized users, separated from routine user accounts where supported, logged, reviewed quarterly, and removed when no longer required.
14. `AC-14` Contractor-access restrictions: Contractor and vendor access must be time-limited, task-based, approved by an access owner, covered by contract security terms, and disabled when the support task or contract ends.
15. `AC-15` Controlled remote-support sessions: Remote-support sessions must use the approved remote-access tool, require MFA, be limited to authorized support tasks, be logged, and be recorded or otherwise auditable where the tool supports that capability.
16. `AC-16` Authentication and administrative logging: ClinicCloud, migration resources, remote-support tools, privileged actions, account changes, failed logins, patient-record access, and third-party integration activity must generate logs that MedCore can access and review.
17. `AC-17` Break-glass access: Break-glass access must be approved for emergency use only, uniquely assigned, strongly authenticated, logged, time-limited, and reviewed within two business days after each use.
18. `AC-18` Password requirements: Where passwords are used, passwords must meet or exceed vendor-supported strong-password controls, must not be reused across users, and must be changed immediately after suspected compromise.
19. `AC-19` Session security: ClinicCloud and remote-support sessions must use secure session settings, including automatic timeout, reauthentication after timeout or privilege elevation where supported, and termination when the user leaves MedCore or the support task ends.
20. `AC-20` Time-limited exceptions: Exceptions to this policy must be written, justified, risk-assessed, approved by a named approver, assigned compensating controls, given an expiration date, and reviewed before renewal. Open-ended exceptions are prohibited.

Where a required access-control capability depends on ClinicCloud, a migration resource, a remote-support tool, or a third-party integration, MedCore must configure or negotiate that capability before production use.

## 5. Roles and Responsibilities

| Role | Responsibilities |
| --- | --- |
| Chief Operating Officer | Owns this policy on an interim recommended basis, sponsors remediation, approves production readiness, and ensures vendor and helpdesk responsibilities are assigned. |
| Clinical Directors | Approve clinical access roles, clinic-level patient-access rules, minimum-necessary requirements, and quarterly clinical access reviews. |
| System or data owners | Approve access to assigned systems or data, validate least privilege, review access, and request corrections. |
| IT helpdesk contractor | Implements approved account changes, endpoint access controls, remote-support configuration, and access termination under MedCore direction. |
| Managers | Request new, changed, and terminated access promptly and validate that user access matches job duties. |
| Users | Use only assigned accounts, protect credentials, complete MFA, report suspected compromise, and access patient data only for authorized duties. |
| Compliance or security function | Interim recommended owner for access-control oversight, exception review, evidence review, monitoring coordination, and policy maintenance until MedCore creates a formal security function. |
| Third-party service providers | Enforce contractually required access controls, logging, breach notification, support access limits, and termination of access when services end. |

## 6. Enforcement

MedCore must monitor and audit compliance with this policy through access reviews, authentication logs, administrative logs, remote-support records, and vendor evidence. Suspected violations must be investigated. Corrective action may include access suspension, forced credential reset, removal of privileged access, additional training, contract remedies, or disciplinary action consistent with applicable employment, contract, and organizational rules. Specific legal penalties are not defined by this policy.

## 7. Exceptions

Policy exceptions require a written request, business justification, risk assessment, compensating controls, named approver, expiration date, and periodic review. Exceptions must be tracked until expiration or closure. Emergency break-glass access must be logged and reviewed after use, even when prior approval was not practical.

## 8. Review and Approval

This policy must be reviewed at least annually, after material system changes, after significant incidents, and after major regulatory changes. Updates must be approved by the designated approving authority and communicated to affected MedCore users, contractors, and service providers.

## 9. Policy Mapping

| Policy ID | Related Risk IDs | Related Gap IDs | NIST CSF 2.0 References | Verification Evidence |
| --- | --- | --- | --- | --- |
| AC-01 | R-01, R-03, R-13 | G-12, G-14 | PR.AA-01, PR.AA-05 | User account export showing named unique accounts |
| AC-02 | R-01, R-03, R-13 | G-12, G-14 | PR.AA-01, PR.AA-05 | Shared-account exception register and account review record |
| AC-03 | R-01, R-04 | G-13 | PR.AA-03 | ClinicCloud MFA configuration report and test login |
| AC-04 | R-01, R-05 | G-13, G-16 | PR.AA-03, PR.DS-02 | MFA evidence for remote, privileged, and migration access |
| AC-05 | R-01, R-02, R-03 | G-14 | PR.AA-05 | Approved access matrix and least-privilege test results |
| AC-06 | R-01, R-02, R-03 | G-04, G-14 | GV.OC-03, PR.AA-05 | Minimum-necessary access rules and sample patient-access test |
| AC-07 | R-02 | G-14 | PR.AA-05 | Clinic-level access configuration and cross-clinic denial test |
| AC-08 | R-02, R-03, R-11, R-13 | G-12, G-14 | PR.AA-01, PR.AA-05 | Approved access request records |
| AC-09 | R-02, R-13 | G-14 | PR.AA-05 | Role catalog and user-to-role assignment report |
| AC-10 | R-13 | G-09, G-12, G-14 | ID.AM-08, PR.AA-01, PR.AA-05 | Role-change ticket closed within 24 hours |
| AC-11 | R-13 | G-09, G-12 | ID.AM-08, PR.AA-01 | Terminated-user deactivation report |
| AC-12 | R-02, R-13 | G-14, G-19 | PR.AA-05, PR.PS-04 | Quarterly access-review record |
| AC-13 | R-05, R-10 | G-02, G-12, G-14, G-19 | GV.RR-02, PR.AA-01, PR.AA-05, PR.PS-04 | Privileged-access list and quarterly review evidence |
| AC-14 | R-03, R-05, R-08, R-09, R-12, R-13 | G-10, G-11, G-12 | ID.RA-10, GV.SC-05, PR.AA-01 | Contractor/vendor access approval and termination evidence |
| AC-15 | R-04, R-05, R-12 | G-11, G-16, G-19, G-20 | GV.SC-05, PR.DS-02, PR.PS-04, DE.CM-06 | Remote-support configuration report and session log |
| AC-16 | R-01, R-02, R-03, R-05, R-06, R-07, R-08, R-09, R-10, R-11, R-12 | G-19, G-20, G-22 | PR.PS-04, DE.CM-03, DE.CM-06, DE.CM-09, RS.CO-02 | Log-access evidence and audit-log review record |
| AC-17 | R-06, R-07, R-10, R-14 | G-19, G-21, G-23 | PR.PS-04, ID.IM-04, RC.RP-03 | Break-glass use log and post-use review |
| AC-18 | R-01, R-04 | G-13, G-24 | PR.AA-03, PR.AT-01 | Password policy configuration and reset evidence |
| AC-19 | R-01, R-04 | G-13, G-19 | PR.AA-03, PR.PS-04 | Session timeout configuration and test evidence |
| AC-20 | R-03, R-05, R-07, R-13 | G-01, G-12, G-14 | GV.PO-01, PR.AA-01, PR.AA-05 | Exception register with expiration dates and approvals |
