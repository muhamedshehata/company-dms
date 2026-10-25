# ADR-006: Document Deletion Request Policy

- **Status:** Accepted — Initial Design Direction
- **Date:** 2026-10-25

## Context

Documents may be subject to business, audit, legal, or retention requirements. Uncontrolled deletion could cause loss of important records or violate applicable retention obligations.

## Decision

Deleting a document requires a request and review by an authorized person.

- Ordinary employees may request deletion but may not execute it directly.
- The request must include a reason and identify the document.
- An authorized reviewer must verify the request and applicable retention requirements.
- Deletion may proceed only when permitted by the approved retention policy and applicable obligations.
- The system must record the requester, reason, review decision, executing user, and timestamps.
- Audit records must remain protected and traceable after an allowed deletion.
- The system must not allow deletion to bypass access controls, retention requirements, or applicable legal holds.

## Initial Boundaries

- The exact roles allowed to approve and execute deletion remain to be defined.
- Retention periods and document-specific rules have not yet been approved.
- The technical meaning of deletion, including recoverability and removal from backups, remains to be defined.
- Legal, regulatory, and company retention requirements must be validated before production use.

## Consequences

- The DMS must support deletion requests, authorization checks, review decisions, and audit records.
- Tests must verify that ordinary employees cannot delete documents directly.
- Tests must verify that deletion is blocked when retention requirements or legal holds prohibit it.
- Deletion must not silently erase the audit trail.

## Review

This decision records the initial policy and must be validated with company stakeholders before production use.
