# ADR-009: Backup and Recovery Strategy

- **Status:** Accepted — Initial Direction Pending Management Approval
- **Date:** 2026-10-25
- **Decision owner:** Project owner

## Context

The DMS is intended for cloud-first production hosting, as documented in ADR-010. Backup and recovery must protect document files and the associated system data against accidental deletion, corruption, unauthorized changes, and service or infrastructure failures.

The final cloud provider and architecture have not yet been selected. Backup capabilities and responsibilities must therefore be evaluated as part of the architecture decision.

## Decision

A documented backup and recovery strategy is required before production use.

Backups must cover the data and configuration needed to restore the DMS to a consistent and usable state. Backup and recovery procedures must be tested before production launch and periodically thereafter.

Any recovery objectives in this document are preliminary proposals only. They are not approved operational commitments until management reviews and approves them.

## Backup Scope

The strategy must account for:

- Original document files and their stored versions.
- Database records, metadata, and relationships to stored files.
- User, role, department, and permission configuration.
- Workflow history and relevant application configuration.
- Audit records required for accountability and investigation.

The restoration process must preserve the relationships between document records, stored files, versions, permissions, and audit history.

## Protection Requirements

- Backups must be protected against unauthorized access, modification, and deletion.
- Backup copies must be isolated from failures that could affect the primary production data.
- Encryption and access controls must be evaluated for backup data and backup transfers.
- Backup integrity must be verifiable.
- Backup responsibilities and monitoring must be documented.
- Backup retention must be defined and must align with approved retention, legal, and business requirements.
- Production documents and credentials must not be committed to the GitHub repository.

## Recovery Requirements

- Documented procedures must exist for restoring the database, document files, configuration, and required audit records.
- Recovery procedures must address consistency between the database and stored files.
- Restoration must be tested using an approved test environment and appropriate non-production data.
- Recovery tests must record the outcome, issues found, and corrective actions.
- Recovery procedures must identify the authorized personnel and the conditions for initiating recovery.

## Preliminary Recovery Objectives

A preliminary proposal is to target no more than 24 hours of data loss, expressed as a Recovery Point Objective (RPO).

This is a proposal for evaluation, not an approved service level. Management must review the business impact, feasibility, and cost before approval.

The Recovery Time Objective (RTO), backup frequency, retention period, number of backup copies, and final recovery design remain undecided.

## Architecture Evaluation

The architecture evaluation must consider:

- Available backup and point-in-time recovery capabilities.
- Independent protection of backups from primary environment failures.
- Data location and applicable legal or contractual requirements.
- Security, encryption, access control, and auditability.
- Recovery testing, operational responsibilities, and monitoring.
- Total cost and expected data growth.
- Recovery of both database records and document files as a consistent system.

Cloud provider selection must not be treated as approval of a backup strategy by itself.

## Acceptance Criteria Before Production

Before production launch:

- The backup scope and responsibilities are documented.
- Backup frequency and retention are approved.
- RPO and RTO are reviewed and approved by management.
- Backup protection and access permissions are configured.
- A restoration test demonstrates recovery of the required data and relationships.
- Test results and unresolved risks are documented and reviewed.

## Open Questions

- What RPO and RTO does the business require and approve?
- How frequently must backups run?
- How long must each backup be retained?
- How many independent backup copies are required?
- Which backup location and protection model will be used?
- Who is responsible for monitoring backups and performing restoration?
- How often must restoration tests be conducted?
- Which legal, contractual, and business retention requirements apply to backups?

## Review Conditions

Review this decision during cloud architecture selection and before production launch. Revisit it when business recovery requirements, data volume, security requirements, or the selected cloud services change.
