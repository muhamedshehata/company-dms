# Company Document Management System (DMS)

**Document ID:** DOC-PROJ-001
**Version:** 1.0-draft
**Status:** Draft — Pending Review
**Last Updated:** 2026-10-25

## 1. Project Purpose

Build a custom Document Management System (DMS) for the company to manage, classify, search, retrieve, secure, and track business documents throughout their lifecycle.

The system must support both the migration of existing paper archives and the ongoing intake of new paper and digital documents.

## 2. Business Context

The currently known project context is:

- Approximately 14,500 legacy pages require assessment and potential digitization.
- Approximately 20 users are expected.
- Departments include Accounting, Finance, HR, Purchasing, Sales, and Management.
- The company uses Odoo.
- Microsoft 365 is available.
- An existing Windows server is available as company infrastructure; it is not the selected direction for production DMS hosting.
- A Canon imageFORMULA DR-M160II document scanner is available.

These are discovery inputs, not a complete or verified requirements specification.

## 3. Project Objectives

1. Create a searchable digital archive.
2. Support scanning and ingestion of new documents.
3. Associate documents with structured metadata.
4. Enforce role-based access permissions.
5. Maintain document history and audit records.
6. Support backup and recovery.
7. Provide a documented path for future Odoo and Microsoft 365 integration.
8. Follow a cloud-first production hosting direction while keeping the document storage implementation replaceable.
9. Establish automated tests for documented business rules.

## 4. Initial Scope

The planned initial product may include:

- Document upload and scanning workflows.
- Document classification and metadata.
- OCR and full-text search.
- Document preview and retrieval.
- User authentication and authorization.
- Audit logging and version history.
- Backup and recovery procedures.
- Administrative functions.

The exact MVP scope will be approved in the requirements phase.

## 5. Out of Scope for Initial Approval

The following are not yet approved as initial-release features or final technical selections:

- AI-based document decisions or autonomous approvals.
- Electronic signatures or digital seals.
- Automated deletion of original paper records.
- Production integration with Odoo.
- Production integration with Microsoft 365.
- Selection of a final cloud provider, application hosting model, database service, or document storage service.

These may be considered or finalized after requirements and architecture evaluation. Cloud-first production hosting is the current project direction; the specific provider and architecture remain undecided.

## 6. Architecture Direction

The selected product direction is a custom-built DMS with cloud-first production hosting, as documented in ADR-010.

The application must keep business logic independent of a specific physical storage path or storage vendor. Document storage should be accessed through a replaceable abstraction where practical.

The cloud provider, application hosting model, database, document storage service, application framework, and OCR engine remain undecided pending architecture evaluation.

The existing Windows server remains part of the company's available infrastructure but is not the default production hosting target under the current cloud-first direction.

## 7. Security and Confidentiality

- The GitHub repository must remain private.
- Real company documents and sensitive company data must not be committed to the repository.
- Test fixtures and examples must use synthetic data.
- Secrets, passwords, API keys, and production credentials must not be committed.
- Access to documents must follow least-privilege principles.
- Applicable Saudi legal, tax, privacy, and record-retention requirements must be validated before production use.

## 8. Delivery Approach

The project will proceed through documented milestones:

- M0 — Project Foundation
- M1 — Requirements and Document Discovery
- M2 — Technical Architecture
- M3 — Minimum Viable Product (MVP)
- M4 — Pilot
- M5 — Legacy Archive Migration
- M6 — Workflow Automation
- M7 — Odoo and Microsoft 365 Integration
- M8 — Security, Audit, Backup, and Retention
- M9 — AI Capabilities
- M10 — Production Launch and Handover

Milestone scope and completion criteria must be documented before implementation.

## 9. Business Logic Governance

- Business rules must be documented before implementation.
- Requirements and acceptance criteria must be reviewable.
- Code changes must include relevant tests.
- Changes to approved decisions must be recorded.
- Claude Code is an implementation assistant, not the final authority on business requirements.
- Human review is required before changes are merged into the main branch.

## 10. Open Questions

- What are the complete document types in each department?
- What metadata is required for each document type?
- What are the actual approval and retrieval workflows?
- Which Odoo version and deployment model are in use?
- Which Microsoft 365 licenses are available?
- Which cloud provider and application hosting model best fit the requirements?
- Which database, application framework, and OCR engine best fit the requirements?
- What retention and disposal policies apply to each document category?
- What backup, recovery, data-location, security, and availability targets are required?

## 11. Approval

This document is a draft until reviewed and approved by the project owner.

Approval must be recorded through a documented review or commit.
