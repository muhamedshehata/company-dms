# ADR-007: Document Retention Policy

- **Status:** Accepted — Initial Direction Pending Management Approval
- **Date:** 2026-10-25

## Context

The company has not yet approved a formal document retention policy. Retention periods and disposal rules may differ by document type and must not be invented by the DMS project team.

## Decision

The DMS must support a configurable document retention policy, but actual retention periods and rules must be approved by company management before they are enforced in production.

- No retention period may be treated as officially approved until management confirms it.
- Retention rules must be configurable by document type where required.
- The system must not permanently delete production documents based on unapproved retention periods.
- Deletion requests must follow ADR-006 and must be checked against the approved retention policy before execution.
- Documents subject to an applicable legal hold or an authorized deletion restriction must not be deleted while that restriction remains in effect.
- Changes to approved retention rules must be authorized and auditable.
- The project must record retention requirements that remain unresolved and assign them for management review.

## Initial Boundaries

- No retention periods have been approved.
- The responsible management approver and the process for approving retention rules remain to be identified.
- Document-type-specific retention periods, start dates, exceptions, and disposal procedures remain undefined.
- Legal, regulatory, contractual, and company requirements must be validated by the appropriate responsible parties before production enforcement.
- Test environments may use synthetic documents and explicitly defined test rules to validate retention behavior.

## Consequences

- The DMS design must allow retention rules to be configured without hardcoding unapproved periods into business logic.
- Production deletion must remain blocked until the applicable retention requirements and authorization rules have been approved and configured.
- Acceptance tests must verify that unapproved retention rules cannot trigger permanent deletion.
- Acceptance tests must verify that applicable deletion restrictions prevent deletion.
- Retention-policy changes and deletion decisions must be traceable through audit records.

## Review

This decision documents the current absence of an approved retention policy. It must be reviewed with company management and the appropriate compliance or legal stakeholders before retention enforcement or permanent deletion is enabled in production.
