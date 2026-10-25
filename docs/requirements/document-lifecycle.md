# DMS Document Lifecycle and Intake Rules

- **Document ID:** DOC-REQ-003
- **Version:** 0.1-draft
- **Status:** Draft — Pending Review
- **Last Updated:** 2026-10-25

## 1. Purpose

Define the initial lifecycle of documents entering the DMS, including classification, validation, review, availability, correction, and archival.

## 2. Core Principles

- Preserve the original uploaded or scanned file.
- Enforce access permissions at every lifecycle stage.
- Record relevant status changes and user actions in the audit history.
- Configure workflow requirements by document type.
- Do not treat rejection or a request for correction as document deletion.
- Keep legacy archive import separate from normal new-document intake.

## 3. Proposed Lifecycle States

### Received

The file has entered the system but has not completed classification and validation.

### Incomplete or Needs Correction

Required metadata is missing, or the document type or classification is incorrect.

The document must be returned to its submitting employee, where applicable, for correction. The system must retain the attempt and its relevant history.

### Pending Review

The document has passed the required intake checks but needs review or approval under its configured document-type workflow.

### Available

The document has passed the checks and any required approval. It is available only to users authorized to access it.

### Archived

The document is retained under the applicable archival policy. Archival status does not override access permissions or retention requirements.

## 4. New-Document Intake Rules

1. An authorized employee uploads a file or initiates a scan.
2. The system records the submission and preserves the original file.
3. The document is classified and the required metadata is supplied.
4. The system validates required fields and access-control settings.
5. If required information is missing or the classification is incorrect, the document is returned for correction.
6. The system records the correction request, relevant status changes, and subsequent resubmission.
7. If validation succeeds, the workflow configured for that document type determines whether the document proceeds directly to availability or to review.
8. A document becomes available only after all applicable checks and required approvals are complete.
9. Every view, download, edit, or other protected action remains subject to authorization.

## 5. Correction and Resubmission

- The system must identify the reason for requesting a correction.
- The submitting employee or another explicitly authorized user may correct the relevant metadata or classification.
- The system must retain the correction history, including who made the change and when.
- The original file must not be silently overwritten.
- If the file itself must be replaced, the system must preserve the previous version or otherwise retain an auditable record of the replacement.
- Resubmitted documents must pass the required validation checks again.
- The exact notification mechanism and correction deadlines remain undecided.

## 6. Legacy Archive Import

Legacy paper and digital documents may be imported through a separate process.

- The import process must support incomplete or uncertain metadata.
- Imported records may be marked for later classification or correction.
- Missing historical information must not be fabricated.
- The original source file or scan must be preserved.
- The rules for making imported documents searchable and available must be defined before the migration pilot.

## 7. Audit History

The system should record, as applicable:

- Document creation or intake.
- Submission and resubmission.
- Classification and metadata changes.
- Correction requests and their reasons.
- Review and approval decisions.
- Availability and archival status changes.
- User identity and timestamp for relevant actions.

Audit records must be protected against unauthorized alteration.

## 8. Acceptance Tests

1. A document missing required metadata is not made available prematurely.
2. A document with an incorrect classification can be returned for correction.
3. The correction request includes a reason.
4. The system retains the submission and correction history.
5. Resubmission triggers the required validation checks.
6. The original file is not silently overwritten during correction.
7. A document requiring approval remains unavailable until required approval is complete.
8. A routine document can become available without manual approval when its configured rules permit it.
9. Availability never bypasses document permissions.
10. Legacy imports can be flagged for incomplete metadata without inventing missing information.

## 9. Open Decisions

- Final lifecycle states and permitted transitions.
- Required metadata by document type.
- Who can classify, correct, review, approve, and archive each type.
- Whether a correction can change the file itself or only its metadata.
- Notifications, reminders, and correction deadlines.
- Retention, deletion, and legal-hold rules.
- Legacy-import validation and availability policy.
- Final approval by company stakeholders.

## 10. Approval

This document is a draft of the initial workflow requirements. Production behavior must not be finalized until the relevant business rules are reviewed and approved.
