# Tools — Client Intake Agent

## Practice Management Systems

- **Clio Grow / Clio Manage** — new matter creation (client record, matter record, responsible attorney assignment, practice area, billing method, retainer amount), client portal invitation, engagement letter template population and send, intake form delivery and collection, trust accounting setup.
- **MyCase** — matter open workflow, client intake forms, case information collection, billing setup, retainer request, e-signature for engagement letter.
- **Filevine** — project creation, contact intake (party type, entity type, contact details), intake questionnaire assignment, document generation for engagement letter.
- **Smokeball** — matter creation wizard, auto-fill from court data, time and billing setup, law library document assembly for engagement letters.

## Document Generation

- **HotDocs / Contract Express** — template-driven engagement letter assembly; auto-population from collected intake data; output in Word and PDF.
- **Lawyaw / Draftwise** — court form auto-fill and engagement document generation; jurisdiction-specific templates.

## E-Signature

- **DocuSign** — send engagement letter for client signature, track envelope status, retrieve executed copy for DMS filing.

## Identity Verification (KYC/AML)

- **Acuant / Jumio** — client identity document verification for matters requiring KYC; returns verification status, confidence score, and document data for AML compliance file.

## Workspace

- **workspace_write** — save the completed intake summary (matter number, client details, conflict-clear confirmation, engagement letter status) for handoff to billing-time-agent and docket-management-agent.

## Data Sources

### Practice Management

- **Clio** — client records (client ID, name, entity type, address, phone, email, referral source, client since date), matter records (matter ID, client ID, matter name, description, practice area, open date, status, responsible attorney, originating attorney, billing attorney, billing method, rate, retainer amount, retainer replenishment threshold), engagement letter templates (template ID, practice area, jurisdiction, version, content), conflict check results (check ID, matter, result, cleared-by, cleared-date)
- **MyCase / Filevine** — equivalent matter and client fields; intake questionnaire responses (question text, response, submitted date, submitted by)

### Engagement & Billing Setup

- **Billing rate tables** — timekeeper rates (attorney/paralegal ID, billing rate, effective date, matter-specific overrides, currency), billing arrangement types (hourly, flat fee, contingency, hybrid, capped fee)
- **Retainer templates** — minimum retainer by matter type and practice area, replenishment schedule, trust account assignment

### Identity & Compliance

- **KYC/AML records** — verification request (client name, document type, submission date), verification result (status: pass/fail/review, confidence score, extracted name, document number, expiry, issuing country), AML risk classification (risk tier, basis, review date)
- **Engagement letter archive** — executed engagement letters (client name, matter number, execution date, signatory, file path in DMS, envelope ID)
