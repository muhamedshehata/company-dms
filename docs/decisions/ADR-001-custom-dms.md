# ADR-001: Choose a Custom Document Management System

- **Status:** Accepted
- **Date:** 2026-10-25
- **Decision owner:** Project owner

## Context

The company needs a document management system for approximately 14,500 existing pages and ongoing document intake across multiple departments.

The system must support structured metadata, document search, access control, auditability, and future integrations.

## Decision

Build a custom Document Management System (DMS) rather than committing to a ready-made DMS product as the primary application.

## Reasons

- Business workflows and metadata can be tailored to the company.
- Integration with Odoo can be designed around the company's requirements.
- Storage and OCR implementations can be replaceable.
- Business rules can be documented and tested.
- The system can evolve through controlled, reviewed changes.

## Consequences

- The company will own the application design and maintenance responsibilities.
- Security, backup, recovery, testing, and deployment must be deliberately engineered.
- The technology stack must be selected after requirements discovery.
- The project must not begin full-scale archive migration before a successful pilot.

## Alternatives Considered

- A ready-made document management product.
- A Microsoft 365 / SharePoint-centered solution.
- A hybrid solution.

These alternatives have not been fully evaluated for cost, licensing, operational complexity, or suitability.

## Review Conditions

Revisit this decision if requirements discovery or technical feasibility shows that a custom application is not justified.
