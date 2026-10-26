# Cloud Hosting and Security Requirements

- **Document ID:** DOC-SEC-002
- **Version:** 0.1-draft
- **Status:** Draft — Pending Review
- **Last Updated:** 2026-10-26

## 1. Purpose

Define the hosting, infrastructure security, and provider-evaluation requirements for the custom Document Management System (DMS).

This document supports architecture evaluation. It does not select a cloud provider, approve a subscription, establish legal compliance, or authorize production deployment.

## 2. Scope and Related Documents

This document covers:
- Hosting and deployment security.
- Data location and provider due diligence.
- Identity and privileged access to hosting resources.
- Encryption and secret management.
- Security monitoring and incident response.
- Security-related architecture acceptance criteria.

Related documents:
- `docs/requirements/access-control-matrix.md` — application and document authorization.
- `docs/decisions/ADR-009-backup-recovery.md` — backup, restoration, and recovery requirements.
- `docs/decisions/ADR-010-cloud-first-hosting.md` — cloud-first hosting direction and architecture evaluation.
- `docs/architecture/architecture-options.md` — preliminary comparison of candidate architectures.

These documents should be read together. This document does not replace their requirements.

## 3. Confirmed Context and Constraints

- Production hosting is intended to be cloud-first.
- The company has no Microsoft 365 subscription.
- No cloud provider, hosting region, paid service, or subscription has been approved.
- The DMS may contain confidential HR, financial, purchasing, sales, and management records.
- Applicable data classifications, contractual obligations, and data-location requirements have not yet been confirmed.
- The final application framework, identity provider, database, document-storage service, and deployment model remain undecided.

## 4. Hosting and Environment Separation

- Production services must not be exposed directly to the public internet unless the exposure is explicitly required, justified, and protected.
- Administrative interfaces and management endpoints must be restricted to authorized administrators.
- Development, testing, and production environments must be separated appropriately.
- Production credentials and real company documents must not be copied into development or test environments without explicit authorization and suitable safeguards.
- Non-production testing should use synthetic or appropriately sanitized data.
- Operating systems, application dependencies, and hosting components must receive security updates under a documented maintenance process.
- Unnecessary services, ports, accounts, and public endpoints should be disabled.
- Network access between the application, database, document storage, and administrative services must be restricted to required flows.

## 5. Identity and Privileged Access

- Access to cloud control panels and infrastructure resources must use individually attributable accounts.
- Shared administrator accounts should be avoided.
- Multi-factor authentication must be evaluated and enabled for privileged access where supported.
- Administrative privileges must be limited to the minimum required tasks.
- Application document permissions and cloud infrastructure permissions must be treated as separate control layers.
- Employee access to documents must not imply permission to administer hosting infrastructure.
- Privileged access grants and removals must be documented and reviewed periodically.
- Emergency administrative access must be controlled and auditable.

## 6. Encryption and Secret Management

- Evaluate encryption at rest for stored documents, databases, backups, and other sensitive persistent data.
- Protect data in transit using current, secure transport encryption.
- Access to encryption keys and secret-management services must be restricted.
- Application secrets, API keys, database passwords, and private keys must not be committed to GitHub or embedded in source code.
- Production secrets must be stored and rotated using an approved secret-management process appropriate to the selected architecture.
- Key ownership, recovery, rotation, and revocation responsibilities must be documented before production.
- Encryption and key-management capabilities must be verified for the specific services selected.

Backup-specific protection and restoration requirements are defined in ADR-009.

## 7. Data Location and Provider Due Diligence

Before selecting a provider or region, the project owner and relevant company stakeholders must determine:

- Applicable legal, regulatory, contractual, and customer requirements.
- Data classifications and whether particular document categories have location restrictions.
- Acceptable locations for primary storage, database services, backups, logs, and disaster-recovery copies.
- Whether support access or subprocessors could access company data from other jurisdictions.
- Provider terms for data processing, data export, service termination, and deletion.
- Availability of required services and security capabilities in each candidate region.

A provider's regional presence does not, by itself, prove that every required service, backup copy, log, or support process remains in that region.

No claim of regulatory compliance or Saudi data-residency compliance may be made until the applicable requirements and the selected service configuration have been reviewed by appropriate stakeholders.

## 8. Logging, Monitoring, and Incident Response

- Security-relevant infrastructure and administrative events must be logged where supported and appropriate.
- Logs must be protected against unauthorized access, modification, and deletion.
- Access to logs must be limited to authorized personnel.
- Monitoring must be evaluated for suspicious authentication, privilege changes, unusual access, service failures, and security alerts.
- Logging must avoid unnecessarily recording document contents, credentials, or sensitive personal data.
- Log retention and access requirements must be defined according to approved business, security, and legal requirements.
- An incident-response procedure must identify reporting channels, responsible personnel, containment steps, evidence preservation, recovery coordination, and escalation.
- Monitoring coverage, alert ownership, and response expectations must be agreed before production launch.

Application audit-trail requirements remain governed by the relevant DMS requirements and decisions.

## 9. Security Evaluation of Candidate Architectures

Each candidate architecture must be assessed against:

- Identity and privileged-access controls.
- Network isolation and exposure.
- Encryption and key management.
- Secret storage and rotation.
- Audit logs, monitoring, and incident response.
- Data location and provider data-processing terms.
- Security update and vulnerability-management responsibilities.
- Document and database protection, including the requirements in ADR-009.
- Data export, migration, and secure deletion at service termination.
- Operational workload, support responsibilities, and total cost.

Provider marketing claims alone are not sufficient evidence that a requirement is met. Evaluation should use service-specific documentation, contractual terms, configuration details, and written confirmation where necessary.

## 10. Acceptance Criteria Before Production

Before production use:

- Data classifications and applicable location requirements have been reviewed and documented.
- The selected provider, services, and regions have been evaluated against the requirements in this document.
- Privileged access and environment separation have been configured and reviewed.
- Required encryption and secret-management controls have been verified.
- Logging, monitoring, incident ownership, and escalation procedures are documented.
- Security responsibilities between the company and provider are documented.
- Security gaps and accepted residual risks are recorded and approved by the appropriate stakeholders.
- Backup and recovery acceptance criteria in ADR-009 have been satisfied.

## 11. Open Questions

- Which legal, regulatory, contractual, and customer requirements apply to the company's records?
- Must any data categories remain within Saudi Arabia?
- Which data classifications apply to HR, financial, and other confidential documents?
- Who will own cloud administration, security monitoring, and incident response?
- What identity provider and multi-factor authentication capabilities will be available?
- What log retention and security-alert response expectations are required?
- What budget is available for security and operational services?
- Who has authority to approve residual risks and authorize production launch?

## 12. Approval Gate

This document remains a draft until reviewed by the project owner and relevant company stakeholders.

No provider, region, subscription, or production deployment is approved by this document. Final selection requires documented evidence, cost evaluation, review of applicable obligations, and explicit approval by the appropriate decision-makers.
