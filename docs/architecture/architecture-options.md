# DMS Architecture Options

**Status:** Preliminary Evaluation — No Final Architecture or Provider Approved
**Date:** 2026-10-25

## 1. Purpose

This document compares candidate architectures for the company's custom Document Management System (DMS). It supports evaluation and decision-making; it does not approve a cloud provider, subscription, purchase, or final architecture.

## 2. Confirmed Context

- The project direction is a custom DMS with cloud-first production hosting.
- The company has no Microsoft 365 subscription, so SharePoint availability and licensing must not be assumed.
- Approximately 14,500 paper pages have been identified for discovery and potential digitization.
- Approximately 20 users across Accounting, Finance, HR, Purchasing, Sales, and Management are expected.
- Odoo is the ERP system; integration requirements remain unconfirmed.
- The company has an existing Windows server, but it is not the selected production hosting direction.
- No cloud provider, paid service, or subscription has been approved.
- Document types, actual digital storage volume, retention periods, recovery targets, and data-location requirements need further verification.

## 3. Candidate Architectures

### Option A — Custom Application with Managed Cloud Services

A custom DMS application using a managed database and a separate cloud document/object-storage service.

**Potential advantages**
- Separates document storage from application logic and metadata.
- May reduce routine infrastructure administration compared with self-managed servers.
- Can support independent evaluation of database and document-storage services.
- Can preserve storage portability if the application uses a replaceable storage abstraction.

**Questions and risks**
- Availability of required services in an acceptable region must be verified.
- Full costs, including storage, requests, backups, OCR, network transfer, monitoring, and support, are unknown.
- Identity, permissions, encryption, audit, and recovery capabilities must be validated for the selected services.

### Option B — Custom Application with SharePoint Storage

A custom DMS application using SharePoint as its document-storage platform, if a suitable subscription is purchased and the required capabilities are available.

**Potential advantages**
- May benefit from SharePoint document-management capabilities and existing Microsoft ecosystem compatibility if separately licensed.
- Could reduce the need to build some storage-related features, subject to detailed requirements and integration design.

**Questions and risks**
- The company has no Microsoft 365 subscription; licensing and total cost must be assessed.
- Required SharePoint capabilities, access controls, APIs, audit features, data location, and backup arrangements must be verified.
- The custom application must not assume that SharePoint automatically satisfies all DMS requirements.

### Option C — Custom Application on a Cloud Virtual Machine

A custom application deployed on a cloud virtual machine, with its database and document storage either hosted on that machine or separated into appropriate services.

**Potential advantages**
- Provides flexibility over the application runtime and deployment configuration.
- May allow reuse of familiar server-administration skills.

**Questions and risks**
- The team may need to manage operating-system updates, application deployment, monitoring, database maintenance, security hardening, and recovery.
- Storing the database and all documents on one machine could increase the impact of a machine or disk failure.
- Costs and operational workload depend on the final design and service choices.

## 4. Preliminary Comparison

| Evaluation criterion | Option A: Managed cloud services | Option B: SharePoint storage | Option C: Cloud VM |
|---|---|---|---|
| Initial purchase and setup cost | Needs quotation and sizing | Subscription and integration cost unknown | VM and setup cost unknown |
| Ongoing total cost | Needs calculation | Licensing and related service costs need calculation | Compute, storage, backups, and administration need calculation |
| Infrastructure administration | Potentially lower | Depends on application and integration design | Potentially higher |
| Storage portability | Good if abstraction is implemented | Depends on integration and export design | Depends on storage design |
| Microsoft 365 dependency | Not required by this option | Requires a suitable SharePoint subscription | Not inherently required |
| Saudi data-location suitability | Must verify by service and region | Must verify for the contracted services and data | Must verify by provider, region, and services |
| Backup and recovery | Validate database and file recovery together | Validate SharePoint recovery and independent protection | Design and test the full recovery process |
| Odoo integration | Requirements and API design needed | Requirements and API design needed | Requirements and API design needed |
| OCR and full-text search | Select and evaluate services | Evaluate built-in and additional capabilities | Select, deploy, and maintain suitable components |
| Final status | Baseline for evaluation | Alternative requiring licensing analysis | Alternative requiring operations and cost analysis |

This comparison is qualitative. It is not a vendor benchmark, quote, or final ranking.

## 5. Evaluation Criteria

Before selecting an architecture, evaluate:

1. Total cost of ownership, including setup, subscriptions, storage growth, OCR, backups, support, and staff time.
2. Data classification, contractual obligations, and applicable data-location requirements.
3. Availability of required services in approved regions.
4. Authentication, authorization, auditability, encryption, and administrative access controls.
5. Backup isolation, recovery-point objective (RPO), recovery-time objective (RTO), and tested restoration.
6. Compatibility with Odoo and any future Microsoft 365 use.
7. OCR quality, Arabic and English search, document preview, and expected workload.
8. Storage portability, export capability, and avoidance of unnecessary vendor lock-in.
9. Operational ownership, monitoring, incident response, and maintenance responsibilities.
10. Ability to scale beyond the initial user count and document inventory.

## 6. Preliminary Recommendation

Use Option A as the baseline for further evaluation, retain Options B and C as alternatives, and do not select a provider or commit to a purchase yet.

This is a provisional evaluation direction, not an approved architecture. Option B must be assessed using actual licensing and service costs rather than assuming Microsoft 365 is already available. Option C must be assessed with its operational workload and recovery responsibilities included.

No option should be approved until data-location requirements, service availability, security controls, full costs, and recovery requirements have been reviewed.

## 7. Open Questions

- Must company documents be stored in Saudi Arabia, or are other locations contractually and legally acceptable?
- What data classifications and confidentiality levels apply, especially to HR and financial records?
- What cloud providers and regions are acceptable to management?
- What are the actual digital file volume, file types, average file sizes, and expected annual growth?
- What are the approved RPO, RTO, backup frequency, and retention requirements?
- What Odoo integration workflows are required?
- Who will administer the DMS and respond to incidents?
- What are the budget limits and procurement constraints?
- Is a Microsoft 365 or SharePoint subscription worth evaluating as a new purchase?

## 8. Approval Gate

Architecture selection requires:
- A documented comparison based on verified service capabilities and current quotations.
- Review of data-location, security, and contractual requirements.
- An agreed operating and support model.
- Approved backup, recovery, and retention requirements.
- Explicit management approval before any paid service or subscription is purchased.
