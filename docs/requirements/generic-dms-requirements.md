# Generic DMS Requirements

- **Document ID:** DOC-REQ-002
- **Version:** 0.1-draft
- **Status:** Draft — Pending Review
- **Last Updated:** 2026-10-25

## 1. Purpose

Build a configurable, general-purpose Document Management System (DMS) that can manage different document types across all company departments without requiring code changes whenever a new document type is introduced.

## 2. Core Design Principles

- Support document types that are configurable by authorized administrators.
- Separate document classification from access permissions.
- Keep document metadata separate from file content.
- Support paper digitization and existing digital files.
- Keep storage and OCR implementations replaceable.
- Require documented, testable business rules.
- Never assume that all employees may access all documents.

## 3. Configurable Document Types

Authorized administrators must be able to:

- Create, rename, deactivate, and manage document types.
- Define required and optional metadata fields for each type.
- Configure field labels, data types, validation rules, and whether a field is required.
- Configure which fields are searchable and filterable.
- Add new document types without changing application code or database schema for each new type.

Deactivating a document type must not delete its existing documents or their history.

Changes to metadata definitions must not silently invalidate existing records.

## 4. Common Document Metadata

The system should support common fields such as:

- Unique document ID.
- Document title.
- Document type.
- Responsible department.
- Creation or issue date, when known.
- Date received or uploaded.
- Source or originating party, when applicable.
- Description and tags.
- Current status.
- Storage reference.
- Created by and last modified by.
- Related documents or business records, when applicable.

Additional fields must be configurable by document type.

The system must distinguish unknown values from confirmed values and must not invent missing metadata.

## 5. Supported Content

The system must be designed to handle:

- Scanned paper documents.
- PDF files.
- Word documents.
- Excel workbooks.
- Image files and other approved file formats.

Supported file formats and their preview, text extraction, and OCR capabilities must be defined and tested before implementation.

Original uploaded files must be preserved. OCR or text extraction must not silently replace the original file.

## 6. Search and Retrieval

The system should support:

- Search by document ID, title, and metadata.
- Filtering by department, document type, date, status, and configured fields.
- Full-text search when text is available through OCR or extraction.
- Preview and retrieval subject to access permissions.
- Search results that do not disclose unauthorized document content or metadata.

## 7. Access Control

The system must enforce permissions based on user identity, department, and assigned role.

Requirements:

- Deny access by default unless explicitly authorized.
- Support permissions for viewing, uploading, editing metadata, downloading, deleting, and administering document types.
- Allow more restrictive permissions for sensitive documents.
- Enforce authorization on the server for every protected operation.
- Apply permissions consistently to search results, previews, downloads, APIs, and document history.
- Restrict permission administration to authorized administrators.
- Record security-relevant permission changes in an audit log.
- Prevent users from granting themselves additional permissions.

Department membership alone must not automatically grant access to every document in that department.

## 8. Audit and Document Integrity

The system should record relevant events, including:

- Document creation and upload.
- Metadata changes.
- Document replacement or new versions.
- Access-permission changes.
- Deletion or deactivation.
- Relevant access and download events, subject to the approved audit policy.

Audit records must identify the actor, action, affected record, and timestamp where applicable.

Ordinary users must not be able to alter or erase audit history.

## 9. Security and Data Protection

- Store production files outside the source-code repository.
- Never commit company documents, credentials, or secrets to GitHub.
- Apply least-privilege access.
- Validate uploads and metadata.
- Define backup, recovery, retention, and deletion policies before production.
- Confirm applicable legal, privacy, and retention obligations with the company.

## 10. Acceptance Criteria

The following tests must pass before the relevant functionality is accepted:

1. An authorized administrator creates a new document type and adds a custom required field without changing application code or database schema.
2. A user cannot submit a document if a required field is missing.
3. Existing documents remain accessible according to their permissions after a document type is deactivated.
4. A user cannot view, search, preview, or download documents outside their permissions.
5. A user cannot bypass permissions by accessing a document through a direct URL or API request.
6. Metadata search and filters return the expected authorized results.
7. OCR or extraction failures do not destroy or replace original files.
8. Permission changes and relevant document changes are auditable.

## 11. Open Decisions

The following remain undecided:

- Application framework and database.
- Metadata storage implementation.
- Exact role and permission matrix.
- Document versioning and deletion policy.
- Supported file size and format limits.
- OCR provider and supported languages.
- Hosting, storage, backup, and recovery design.
- Retention periods and applicable compliance requirements.
- Odoo and Microsoft 365 integration details.

## 12. Approval

This document is a draft. Requirements must be reviewed with the project owner and relevant department representatives before implementation.
