# ADR-002: Keep Storage Provider Replaceable

- **Status:** Accepted
- **Date:** 2026-10-25
- **Decision owner:** Project owner

## Context

A Windows server is available, but cloud storage may be preferable if local deployment proves difficult or unsuitable.

## Decision

Design the application so that business logic does not depend directly on a physical file path or a specific storage vendor.

Local Windows storage is the initial deployment preference, subject to technical validation. Cloud storage remains an option.

## Requirements

- Access files through a storage abstraction.
- Keep document metadata separate from file content.
- Define how stored files are identified and retrieved.
- Consider encryption, access control, backups, recovery, and integrity checks.
- Do not store production documents or credentials in GitHub.

## Consequences

The storage implementation and deployment model remain open until the server, security, capacity, backup, and cost requirements are assessed.

## Review Conditions

Revisit the deployment choice after reviewing server specifications, available storage, network access, backup arrangements, and cloud costs.
