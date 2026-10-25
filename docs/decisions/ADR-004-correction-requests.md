# ADR-004: Correction Requests for Available Documents

- **Status:** Accepted — Initial Design Direction
- **Date:** 2026-10-25

## Context

Documents may contain incorrect metadata or an incorrect file even after they become available to authorized users. Direct, untracked changes could undermine document integrity and auditability.

## Decision

Corrections to available documents must follow a correction-request process rather than allowing submitters to make direct changes.

- The submitter requests a correction and provides the reason and details.
- An authorized person reviews or performs the correction according to configured permissions.
- The system preserves the previous file version when the file is replaced.
- The system records the request, decision, person responsible, timestamps, and relevant changes.
- The corrected document must pass applicable validation and approval rules before the correction becomes effective.
- Access permissions continue to apply throughout the process.

## Initial Boundaries

- The exact reviewer roles and approval rules remain to be defined.
- Whether metadata-only corrections require the same approval process as file replacement remains open.
- Version retention and restoration rules remain to be defined.
- This decision does not authorize permanent deletion of previous versions.

## Consequences

- The DMS must support correction requests, authorization checks, version history, and audit records.
- Tests must verify that unauthorized users cannot modify available documents and that previous versions remain traceable.
- The implementation must not silently overwrite an existing file.

## Review

This decision records the initial policy and must be validated with company stakeholders before production use.
