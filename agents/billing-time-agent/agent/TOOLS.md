# Tools — Billing & Time Agent

## Practice Management / Billing Platforms

- **Clio Manage** — time entry creation and editing (matter, date, timekeeper, hours, description, billing code), pre-bill generation and editing, invoice finalization and delivery, write-off recording, trust ledger queries, AR aging report.
- **Tabs3 Billing** — time entry posting, billing statement generation, LEDES export, write-off workflow, payment recording, trust account reconciliation.
- **TimeSolv** — time tracking, expense entry, billing rate management, invoice creation and delivery, billing guideline enforcement rules.
- **CosmoLex** — combined practice management and legal accounting; trust accounting (IOLTA compliance), billing, AR, and financial reporting in one platform.

## Billing Guideline Compliance

- **Wolters Kluwer ELM Solutions (TyMetrix)** — outside counsel billing guideline enforcement; billing rule validation (block billing flag, vague entry flag, rate deviation, uncovered task codes); UTBMS task and activity code lookup.
- **LegalTracker (Thomson Reuters)** — matter budget tracking, invoice review against guidelines, e-billing submission and status, accrual management.
- **Apperio** — real-time matter spend visibility, budget vs. actuals, invoice reconciliation.

## LEDES / E-Billing

- **LEDES 98B / LEDES XML** — generate LEDES-formatted invoices for submission to corporate law departments; validate UTBMS task codes (L-codes for litigation, A-codes for counseling) and activity codes.

## Workspace

- **workspace_write** — save pre-bill summaries, LEDES export files, and billing exception reports to `/sandbox/.openclaw/workspace/` for attorney review.

## Data Sources

### Time & Billing Records

- **Clio / Tabs3 / TimeSolv** — time entries (entry ID, matter number, client ID, timekeeper ID, date, hours, description, billing code, status: draft/submitted/billed/written-off, rate, amount), expense entries (expense ID, matter number, date, category, amount, description, billable flag, receipt attached), invoices (invoice ID, matter number, client ID, issue date, due date, amount billed, amount paid, balance, status, payment terms)
- **Write-off records** — write-off ID, original entry, write-off amount, reason code, approved by, approval date
- **Trust accounting** — trust ledger (matter number, client name, deposit date, deposit amount, disbursement date, disbursement amount, balance, transaction type), IOLTA account balance, trust-to-operating transfers

### Billing Guidelines

- **Outside counsel billing guidelines (OCBG)** — client name, guideline version, effective date, rate caps by timekeeper level, prohibited task codes, block billing policy, narrative requirements, invoice format requirements, staffing restrictions, budget requirements
- **UTBMS code tables** — task code (L/A prefix, code, description, applicable matter type), activity code (A-prefix, code, description), expense code (E-prefix, code, description)

### AR & Financial

- **AR aging report** — client name, matter number, invoice number, invoice date, days outstanding (0-30, 31-60, 61-90, 90+), balance due, last payment date
- **Billing rate tables** — timekeeper ID, name, title, standard rate, matter-specific rate, effective date, currency, client-approved rate
