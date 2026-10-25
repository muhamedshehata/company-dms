# ADR-002: Keep Storage Provider Replaceable

- **Status:** Accepted — Updated for Cloud-First Direction
- **Date:** 2026-10-25
- **Decision owner:** Project owner

## Context

The project has adopted a cloud-first hosting direction as documented in ADR-010. The production DMS is intended to be hosted in the cloud rather than on a server inside the company. The cloud provider and final storage design have not yet been selected.

## Decision

Design the application so that business logic does not depend directly on a physical file path or a specific storage vendor.

Cloud hosting is the project direction from the beginning. The specific document storage service and overall deployment architecture must be selected after comparing suitable options.

## Requirements

- Access document files through a replaceable storage abstraction.
- Keep document metadata separate from file content.
- Define how stored files are identified and retrieved independently of provider-specific paths.
- Consider encryption, access control, backups, recovery, and integrity checks.
- Do not store production documents or credentials in GitHub.
- Evaluate cloud storage options against security, cost, data location, operational requirements, and integration needs.
- Avoid unnecessary provider-specific dependencies in core business logic.

## Consequences

The application and storage architecture must support cloud deployment while allowing the storage implementation to be replaced where practical.

The final cloud provider, document storage service, database, and application hosting design remain open until the architecture evaluation is complete.

## Review Conditions

Review the storage design against cloud service capabilities, security requirements, expected capacity and growth, network access, backup and recovery arrangements, integration requirements, and total cost.

See ADR-010 for the cloud-first hosting direction and provider evaluation criteria.
