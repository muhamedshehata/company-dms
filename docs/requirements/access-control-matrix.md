# DMS Access Control Matrix

- **Document ID:** DOC-SEC-001
- **Version:** 0.1-draft
- **Status:** Draft — Pending Review
- **Last Updated:** 2026-10-25

## 1. Purpose

Define a configurable, role-based access control model for documents across all company departments.

This matrix is a proposed baseline. Final permissions require review and approval by the project owner and relevant company stakeholders.

## 2. Access Control Principles

- Deny access by default unless permission is explicitly granted.
- Enforce authorization on the server for every protected operation.
- Separate document viewing from editing, downloading, deleting, and administration.
- Combine user identity, assigned roles, department scope, and document-specific restrictions.
- Department membership does not automatically grant access to every document in that department.
- Apply the same authorization rules to search results, previews, downloads, APIs, and document history.
- Log security-relevant actions and permission changes.
- Do not allow users to grant themselves permissions.

## 3. Proposed Roles

### Employee

A regular employee who accesses documents within their explicitly authorized scope.

### Department Manager

A manager who accesses documents within an approved departmental scope and performs additional actions only where explicitly authorized.

### System Administrator

An administrator responsible for technical system administration, user administration, and system configuration.

**Confirmed project decision:** The System Administrator may view all documents, including confidential documents.

This viewing permission does not automatically grant permission to edit, delete, approve, or download every document.

### Permission Administrator

An optional role responsible for assigning and reviewing access permissions. The company may assign this responsibility to an existing role or a separate person.

## 4. Preliminary Permission Matrix

Legend:
- **Yes:** Included in the proposed baseline.
- **Scoped:** Only within the user's explicitly authorized scope.
- **Separate grant:** Requires an additional explicit permission.
- **Pending:** Requires business approval.

| Action | Employee | Department Manager | System Administrator | Permission Administrator |
|---|---|---|---|---|
| View documents | Scoped | Scoped | All documents | Scoped |
| Search documents | Authorized results only | Authorized results only | All documents | Authorized results only |
| Upload documents | Scoped | Scoped | Separate grant | Separate grant |
| Edit metadata | Separate grant or scoped permission | Scoped | Separate grant | Separate grant |
| Download documents | Scoped | Scoped | Separate grant | Separate grant |
| Delete documents | Separate grant | Separate grant | Separate grant | Separate grant |
| Manage document types and custom fields | No by default | No by default | Yes | No by default |
| Manage users | No | No by default | Yes | No by default |
| Assign access permissions | No | No by default | Pending | Yes, if assigned |
| View audit records | Scoped if authorized | Scoped if authorized | Pending | Scoped if authorized |
| Change system settings | No | No | Yes | No by default |

This matrix is provisional. A role must not receive a permission solely because of its name or job title.

## 5. Confidential Documents

- Documents may be restricted to specific users, roles, departments, or approved groups.
- Document-level restrictions may be more restrictive than the department's default permissions.
- The System Administrator retains the confirmed ability to view all documents.
- Other actions on confidential documents remain subject to their separately assigned permissions.
- Confidential document titles, metadata, search snippets, and previews must not be exposed to unauthorized users.
- Access to sensitive documents should be auditable.

## 6. Permission Assignment

Permissions should be configurable without application code changes.

The system should support:

- Assigning one or more roles to a user.
- Associating users with departments.
- Defining permissions for document types and individual documents.
- Restricting access to particular documents where required.
- Reviewing and revoking permissions.
- Recording who changed permissions, what changed, and when.

Permission inheritance and conflict resolution rules must be defined before implementation. More permissive access must not silently override a confidentiality restriction.

## 7. Security Requirements

- Validate permissions on the server for every protected operation.
- Do not rely on hiding buttons or interface elements as the only security control.
- Prevent direct URL or API access from bypassing permissions.
- Ensure unauthorized search results do not disclose restricted information.
- Record permission changes and relevant administrative actions.
- Protect audit history from alteration by ordinary users.
- Review privileged accounts and remove unnecessary access.
- Define an emergency access procedure if the company requires one.

## 8. Acceptance Tests

1. An employee cannot view a document outside their authorized scope.
2. A department manager cannot automatically access all departments' documents.
3. The System Administrator can view confidential documents across all departments.
4. The System Administrator cannot edit or delete a document solely because they can view it.
5. A user cannot download a document without download permission.
6. Direct URLs and API requests enforce the same permissions as the user interface.
7. Search results and previews do not reveal unauthorized document information.
8. Permission changes are recorded in the audit log.
9. Revoked access is enforced on subsequent protected requests.
10. Adding a new document type does not bypass existing authorization rules.

## 9. Open Decisions

- Final role definitions and role ownership.
- Whether department managers may approve or delete documents.
- Whether system administrators may download confidential documents by default.
- Who can view and export audit records.
- Whether permission administration must be separated from system administration.
- Rules for document sharing across departments.
- Emergency access, review frequency, and privileged-account monitoring.
- Final approval by company management and relevant stakeholders.

## 10. Approval

This matrix remains a draft until reviewed and approved.

No production access policy should be considered finalized solely on the basis of this document.
