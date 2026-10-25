# ADR-010: Cloud-First Hosting Strategy

- **Status:** Accepted — Initial Direction Pending Architecture Review
- **Date:** 2026-10-25

## Context

The DMS requires secure, reliable storage and access for business documents, metadata, permissions, workflows, and audit records. The project initially considered on-premises Windows Server hosting, but the current direction is to use cloud hosting from the beginning.

## Decision

The project adopts a cloud-first hosting direction instead of hosting the production DMS on a server inside the company.

- The cloud provider has not yet been selected.
- The application, database, and document storage architecture must be evaluated before a final hosting design is approved.
- The initial candidate for evaluation is a custom DMS application hosted in the cloud, using a database service and document storage suited to the requirements.
- Microsoft SharePoint-based document storage and cloud virtual machines remain alternatives to evaluate.
- Document storage must remain replaceable without coupling core business logic to a specific provider or physical storage path.
- Security, access control, auditability, backup, recovery, and data integrity requirements remain mandatory regardless of provider.
- The design must consider integration with Odoo and Microsoft 365 without assuming that either integration is already approved for implementation.

## Evaluation Criteria

The architecture review must compare candidate designs based on:

- Total cost, including hosting, storage, backup, data transfer, licensing, and ongoing operations.
- Security controls, identity integration, permissions, encryption, and audit capabilities.
- Data location and applicable company, privacy, legal, and regulatory requirements.
- Backup and recovery capabilities, including the preliminary RPO target in ADR-009.
- Compatibility with Odoo and Microsoft 365.
- Operational complexity, monitoring, maintenance, and support.
- Scalability and the ability to change storage providers later.

## Initial Boundaries

- No cloud provider has been selected.
- No production subscription, service, or paid resource is approved by this decision.
- The final application hosting, database, document storage, OCR, and networking technologies remain open.
- The architecture must be reviewed before implementation or production deployment.
- The previous preference for on-premises Windows Server must be revisited in the project charter and ADR-002.

## Consequences

- The project must evaluate cloud-based designs before selecting the technology stack.
- Cost and security assumptions must be documented and validated rather than guessed.
- Backup and recovery requirements must be updated to reflect the selected cloud architecture.
- Provider-specific dependencies should be isolated where practical.
- The project must not treat the preliminary candidate design as a final architecture decision.

## Review

This decision records the cloud-first direction only. The provider and detailed architecture require a documented comparison and approval before implementation.
