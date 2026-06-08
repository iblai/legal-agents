# Tools — Contract Review Agent

## Contract Lifecycle Management (CLM)

- **Ironclad** — contract repository, playbook enforcement, redline generation, approval workflows, clause extraction and comparison against standard positions; API supports document upload, playbook run, risk score retrieval, and comment export.
- **ContractPodAi** — AI contract analysis, obligation extraction, key date tracking, deviation reporting against standard templates.
- **Kira Systems** — machine-learning-based clause identification; trained models for M&A due diligence, lease abstraction, and commercial agreements; outputs structured clause data for review.
- **Litera (formerly Workshare / Draftsmith)** — document comparison (blackline generation), clause library management, drafting guidance, and style consistency checks.

## Document Management Systems (DMS)

- **NetDocuments** — retrieve and version contracts stored in the firm DMS; check-in/check-out, version history, related-document links.
- **iManage Work** — matter-centric document retrieval; email filing, version control, and workspace folders.

## E-Signature & Execution

- **DocuSign** — envelope status (sent, viewed, signed, declined), signatory information, completed document retrieval, audit trail.
- **Adobe Acrobat Sign** — alternative e-signature platform; completion certificate and audit trail retrieval.

## Workspace

- **workspace_write** — save risk summary memos, redlined documents, and clause extraction reports to `/sandbox/.openclaw/workspace/` for attorney review or handoff to `brief-drafting-agent`.

## Data Sources

### Contract Lifecycle Management

- **Ironclad** — contract records (contract ID, type, parties, effective date, expiration date, auto-renewal date, governing law, status), playbook results (clause name, detected text, deviation flag, risk tier, recommended language), obligation register (obligation description, owner, due date, recurrence, completion status), approval workflow history (approver, role, action, timestamp)
- **Kira Systems** — clause extraction results (clause type, extracted text, confidence score, page/paragraph location), provision flags (deviation from standard, missing required provision, non-standard definition), due diligence summary reports
- **ContractPodAi** — contract metadata (parties, term, value, renewal notice period), obligation extraction (obligation type, party responsible, trigger condition, deadline), risk score (overall and per-provision)

### Document Management

- **NetDocuments / iManage** — document metadata (document ID, matter number, author, created date, version number, status), version history (prior versions, change summaries, checkout log), related documents (linked agreements, amendments, schedules, exhibits)

### Firm Standard Positions

- **Clause library (internal)** — standard positions by contract type (NDA, MSA, SOW, lease, employment, vendor), acceptable deviations, red-line language, fallback positions, escalation thresholds
- **Playbook database** — playbook name, contract type, clause list, risk thresholds, approved fallback language, last-reviewed date

### Execution & Signature

- **DocuSign** — envelope metadata (envelope ID, sender, recipients, status, sent date, completed date), signatory details (name, email, signed timestamp, IP address), completed document (signed PDF, certificate of completion, audit trail)
