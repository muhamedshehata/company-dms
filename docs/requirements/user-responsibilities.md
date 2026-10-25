# DMS User Responsibilities and Document Ownership

- **Document ID:** DOC-REQ-004
- **Version:** 0.1-draft
- **Status:** Draft — Pending Review
- **Last Updated:** 2026-10-25

## 1. Purpose

Define initial responsibilities for employees and privileged roles when submitting, classifying, correcting, reviewing, and managing documents.

## 2. Confirmed Business Decision

Each employee is responsible for uploading their own documents and entering the document type and required metadata.

The system must validate required information and enforce access permissions independently of the submitting employee.

## 3. Proposed Responsibilities

### Employee / Submitter

- Upload or scan documents they are authorized to submit.
- Select the document type.
- Enter the required metadata.
- Correct incomplete metadata or incorrect classification when a correction is requested.
- Resubmit corrected documents.
- Access documents only within their assigned permissions.
- Not approve their own submissions where independent approval is required by the configured workflow.

### Department Manager

- Access documents within an explicitly authorized scope.
- Review or approve documents only when assigned that responsibility.
- Not automatically gain access to every department's documents.
- Not automatically receive edit, download, or delete permissions solely because of their job title.

### Reviewer / Approver

- Review or approve documents only for document types and workflows assigned to them.
- Record review decisions and reasons where required.
- Request correction when information is missing or incorrect.
- Not bypass access restrictions or alter audit history.

### System Administrator

- Administer technical configuration and user accounts.
- View all documents, as previously confirmed.
- Not automatically gain edit, delete, download, or approval permissions solely from the ability to view all documents.

## 4. Configurable Responsibilities

The DMS should allow authorized administrators to configure, as appropriate:

- Which roles may submit each document type.
- Which metadata fields are required for each type.
- Who may correct document metadata or replace a file.
- Which document types require review or approval.
- Who may review or approve each workflow.
- Which roles may archive or perform other protected actions.

These rules must be configurable without application code changes for each new document type.

## 5. Validation and Audit

- Validate required metadata before a document becomes available.
- Return incomplete or incorrectly classified submissions for correction.
- Record submission, correction, resubmission, review, approval, and relevant status changes.
- Enforce authorization on the server for every protected operation.
- Do not expose unauthorized documents through search results, previews, direct links, or APIs.

## 6. Open Decisions

- Final department-manager responsibilities.
- Whether submitters may edit metadata after a document becomes available.
- Whether submitters may replace an uploaded file after submission.
- Which document types require independent approval.
- Whether self-approval is prohibited for all document types or only selected workflows.
- Who may archive, delete, restore, or place a document on legal hold.
- Final approval by company stakeholders.

## 7. Approval

This document records the confirmed submitter model and proposes initial role responsibilities. Unconfirmed responsibilities remain subject to business review before production implementation.
