# Data Classification and Sensitivity Requirements

**Document ID:** DOC-DATA-001
**Version:** 0.1-draft
**Status:** Draft — Pending Review
**Last Updated:** 2026-10-26

## 1. Purpose

Define an initial framework for classifying documents stored in the Document Management System (DMS). Classification will help determine appropriate access, handling, storage, search, retention, and protection requirements.

This document proposes an initial framework only. It does not establish legal classifications, declare regulatory compliance, or approve final access permissions.

## 2. Scope

The framework applies to documents created, received, uploaded, scanned, indexed, searched, downloaded, shared, archived, or deleted through the DMS.

Relevant business areas include:

- Accounting
- Finance
- Human Resources (HR)
- Purchasing
- Sales
- Management

## 3. Classification Principles

1. Every managed document must have a classification before it becomes generally available through the DMS.
2. Classification must reflect the potential impact of unauthorized access, disclosure, modification, loss, or deletion.
3. The document owner or an authorized business representative is responsible for assigning or confirming the classification, subject to an approved company policy.
4. The DMS must not rely on department membership alone to authorize access.
5. Classification does not replace document-level permissions or the access-control matrix.
6. When classification is missing, invalid, or uncertain, the system must apply a restrictive handling policy until an authorized person resolves it.
7. Classification changes must be authorized and auditable.
8. Legal, regulatory, contractual, and customer requirements must be reviewed before the classification scheme is approved.

## 4. Proposed Classification Levels

These levels are proposed for discussion and require management approval.

### 4.1 Public

Information explicitly approved for public disclosure.

Examples may include approved public brochures or published company announcements.

Public classification does not authorize a user to publish a document; publication must follow the company's approval process.

### 4.2 Internal

Routine business information intended for authorized company use and not approved for public disclosure.

Examples may include internal procedures, routine operational instructions, and non-sensitive internal notices.

### 4.3 Confidential

Information that could cause business, financial, contractual, privacy, or operational harm if disclosed or changed without authorization.

Potential examples include financial reports, purchasing quotations, customer records, sales agreements, and non-public management documents.

### 4.4 Restricted

Highly sensitive information requiring specifically limited access and additional handling controls.

Potential examples may include sensitive employee records, payroll details, bank account information, identity documents, credentials, or particularly sensitive legal and management records.

The company must confirm which information belongs in this level and whether additional categories are needed.

## 5. Proposed Metadata Requirements

The DMS should support the following metadata where applicable:

- Classification level
- Document type
- Owning department
- Document owner or responsible role
- Creation or received date
- Applicable retention rule, once approved
- Review status for missing or disputed classifications

Metadata requirements must be configurable where business needs differ by document type.

Sensitive metadata must receive appropriate access protection. Search results, previews, filenames, and snippets must not reveal confidential information to unauthorized users.

## 6. Classification and Access

- Classification must inform handling requirements but must not independently grant access.
- Access decisions must also enforce user identity, assigned permissions, business need, and any applicable document restrictions.
- Download, export, external sharing, editing, and deletion may require separate permissions.
- Restricted documents may require additional approval or stronger access controls, subject to the approved access-control policy.
- Classification must be preserved when documents are versioned, moved, exported, backed up, or restored.
- Any downgrade in classification must be authorized and recorded.

Detailed authorization rules remain governed by `access-control-matrix.md`.

## 7. Scanned and Historical Documents

For historical paper documents:

1. Record the document type and owning department where known.
2. Assign a provisional classification using an approved mapping or authorized review.
3. Flag unclear or incomplete cases for review.
4. Do not treat OCR output as authoritative evidence of classification.
5. Restrict access to unreviewed batches where their contents may be sensitive.
6. Record the review outcome before broad access is enabled.

A representative sample should be reviewed before classifying the full archive.

## 8. Review and Governance

Before production use, management must identify:

- The person or role authorized to approve the classification scheme.
- The responsible owner for each document category.
- Who may assign, change, or override classifications.
- How classification disputes are resolved.
- How often classifications and mappings are reviewed.
- Which legal, regulatory, contractual, or customer requirements apply.
- Whether additional labels are needed for personal data, financial records, legal holds, or other special cases.

## 9. Acceptance Criteria

The classification framework is ready for implementation planning when:

- The company approves the classification levels and definitions.
- Document types are mapped to proposed default classifications.
- Ownership and review responsibilities are documented.
- Classification behavior for unknown or disputed documents is approved.
- Access-control and audit requirements are aligned with the classification scheme.
- Retention and data-location requirements are reviewed separately.
- A pilot sample demonstrates that employees can classify representative documents consistently.

## 10. Open Questions

- Are these four proposed levels appropriate for the company?
- Which document types exist in each department?
- Which document types contain personal, financial, contractual, or otherwise sensitive information?
- Are there mandatory classifications or handling rules imposed by law, contracts, or customers?
- Who approves classification assignments and changes?
- Should any document types require restricted access by default?

## 11. Approval Status

This document is a draft for review. It does not approve production deployment, final access permissions, legal compliance, or a data-classification decision for any specific document.
