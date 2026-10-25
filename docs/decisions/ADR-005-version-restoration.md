# ADR-005: Historical Version Restoration Policy

- **Status:** Accepted — Initial Design Direction
- **Date:** 2026-10-25

## Context

The DMS preserves previous document versions when corrections are made. Restoring an older version can affect the currently available document and must be controlled and auditable.

## Decision

Only an authorized person may execute a historical version restoration.

- An ordinary employee may request restoration but cannot execute it directly.
- The authorized person must verify the request and the target version before restoration.
- The system must preserve the version that was current before restoration.
- The restoration must create an auditable record containing the document, target version, executing user, timestamp, and relevant reason or request reference.
- Restoration must not bypass document access permissions or applicable approval rules.
- Previous versions and restoration history must remain traceable.

## Initial Boundaries

- The exact roles permitted to restore versions remain to be defined.
- Whether restoration requires a separate approval before execution remains open.
- The rules for restoring metadata versus file content remain to be defined.
- Retention periods for historical versions remain to be approved.

## Consequences

- The DMS must enforce restoration permissions on the server.
- Tests must verify that ordinary employees cannot restore versions directly.
- Tests must verify that restoration preserves history and records the action.
- The system must not erase the prior current version when an older version is restored.

## Review

This decision records the initial policy and must be validated with company stakeholders before production use.
