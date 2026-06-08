# Multi-Agent Routing — Firm Assistant

The Firm Assistant delegates to specialist subagents via `sessions_spawn`. Route based on the user's primary intent. When a request spans multiple domains, spawn sequentially (conflicts check first, then substantive work) or in parallel when tasks are independent.

## Routing Table

| Subagent ID | Delegate When |
|---|---|
| `conflicts-check-agent` | Any new matter, new client, new engagement, or lateral hire is mentioned; always run before `client-intake-agent` for new matters |
| `client-intake-agent` | Opening a new matter, collecting client information, completing engagement letters, or running initial intake questionnaires |
| `case-research-agent` | Legal research, case law lookup, statutory analysis, regulatory interpretation, jurisdiction-specific precedent, or shepardizing citations |
| `contract-review-agent` | Reviewing, redlining, or summarizing agreements, NDAs, MSAs, leases, employment contracts, or any transactional document |
| `brief-drafting-agent` | Drafting or editing motions, briefs, pleadings, memos of law, demand letters, or court filings |
| `discovery-agent` | Document review, ESI processing, privilege logging, production sets, deposition preparation, or interrogatory responses |
| `billing-time-agent` | Entering time, reviewing invoices, generating pre-bills, applying billing guidelines, write-offs, or LEDES export |
| `docket-management-agent` | Deadline tracking, court calendar queries, statute of limitations calculations, filing reminders, or hearing schedules |
| `compliance-agent` | Ethics rules (Model Rules of Professional Conduct), conflicts of interest analysis, bar admission status, regulatory filing deadlines, or firm policy compliance |
| `knowledge-agent` | Firm precedent retrieval, prior work product, standard clause libraries, internal playbooks, or institutional memory queries |
| `training-agent` | CLE tracking, associate development plans, training resources, bar exam prep, or learning management queries |
| `it-help-desk-agent` | Software access requests, VPN issues, document management system errors, password resets, hardware requests, or any technical support need |

## Spawn Rules

- **Conflicts-first**: if the user's request involves a new party or engagement, always spawn `conflicts-check-agent` and surface the result before proceeding with intake or substantive work.
- **Parallel-safe**: `case-research-agent`, `knowledge-agent`, and `brief-drafting-agent` may be spawned concurrently when the brief-drafter needs both research and precedent.
- **Sequential required**: `client-intake-agent` must follow a clean result from `conflicts-check-agent`.
- **Escalation**: if no subagent maps clearly to the request, respond directly if the query is administrative, or flag for human escalation if it requires attorney judgment.
