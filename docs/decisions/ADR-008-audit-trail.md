# ADR-008: Audit Trail and Audit Log Access

- **Status:** Accepted — Initial Design Direction
- **Date:** 2026-10-25

## Context

The DMS must provide traceability for important document, security, workflow, and administrative actions. Audit records may contain sensitive information and must be protected against unauthorized access, alteration, or deletion.

## Decision

The DMS must maintain an audit trail for important system actions.

- Initially, only the System Administrator role may view audit records.
- Audit-log access must be enforced by the server, not merely hidden in the user interface.
- Ordinary employees and department managers must not be able to view audit records unless a future approved decision changes this policy.
- Users must not be able to alter or delete audit records through ordinary application permissions.
- Audit records must identify the relevant actor, action, timestamp, target object where applicable, and outcome where available.
- Audit records must not unnecessarily copy document contents, passwords, credentials, or other secrets.
- Audit records must remain traceable after document correction, version restoration, or an authorized deletion.
- Access to the audit log and changes to security-sensitive settings must themselves be recorded where technically feasible.

## Initial Events to Audit

The initial audit requirements include:

- Successful and failed authentication events, where supported.
- User, role, department, and permission changes.
- Document creation, upload, scanning intake, and classification changes.
- Metadata changes and document correction requests.
- Correction decisions, approvals, rejections, and workflow status changes.
- File replacement and version restoration.
- Deletion requests, decisions, and authorized deletion execution.
- Changes to retention rules and other security-sensitive configuration.
- Attempts to perform unauthorized actions, where technically feasible.

The exact event schema and additional event categories will be refined during technical architecture and requirements review.

## Access and Protection

- Audit-log access must follow server-side authorization.
- Only the System Administrator may view audit records under the initial policy.
- Audit records must be protected from unauthorized modification and deletion.
- Audit data must be included in backup and recovery planning.
- Audit access, retention, export, and protection mechanisms must be tested before production launch.
- Audit records must not expose document titles, metadata, or other sensitive information to users who are not authorized to view those records.

## Initial Boundaries

- The initial audit-log viewer role is the System Administrator.
- Whether a separate audit role is needed remains an open question for management review.
- Audit-log retention duration, export permissions, tamper-evidence mechanisms, and access to audit records during investigations remain to be defined.
- Applicable company, privacy, legal, and regulatory requirements must be validated before production use.

## Acceptance Criteria

- Ordinary employees and department managers cannot view audit records.
- The System Administrator can view audit records.
- Unauthorized users cannot modify or delete audit records.
- Important document and permission changes generate appropriate audit events.
- Correction, restoration, and deletion actions remain traceable.
- Audit records do not unnecessarily expose document contents or secrets.
- Audit-log access and sensitive configuration changes are recorded where supported.
- Audit records are included in the documented backup and recovery plan.

## Review

This decision records the initial audit policy. It must be validated during requirements review and technical architecture before production launch.
