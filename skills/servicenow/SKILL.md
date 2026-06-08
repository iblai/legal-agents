---
name: servicenow
description: ServiceNow ITSM platform; lets an agent create, update, and resolve IT incident and service request tickets and retrieve knowledge base articles.
metadata: {"openclaw":{"requires":{"env":["SERVICENOW_INSTANCE_URL","SERVICENOW_USERNAME","SERVICENOW_PASSWORD","SERVICENOW_CLIENT_ID","SERVICENOW_CLIENT_SECRET"]}},"primaryEnv":"SERVICENOW_PASSWORD"}
---

# ServiceNow

## What it is
ServiceNow is the leading IT Service Management (ITSM) platform used by large and mid-size law firms to manage IT incidents, service requests, change management, and the IT knowledge base. It provides a single pane of glass for help desk operations, SLA tracking, and escalation routing. ServiceNow exposes a comprehensive Table API and scripted REST APIs for all record types.

## When to use this skill
- Creating an incident ticket when a staff member reports a technical issue
- Updating the status, resolution notes, or assignee on an open incident
- Submitting a service request for new access provisioning, equipment, or software installation
- Searching the knowledge base for self-service troubleshooting articles before escalating
- Querying open tickets by requester, category, or SLA status for a status report
- Escalating a ticket to a specialist team (e.g., e-discovery, network, information security)

## Credentials
This skill authenticates using variables declared in the `metadata` frontmatter above. Set them in the OpenClaw daemon env file `~/.openclaw/.env` (see `.env.example` at the config root). Required variables:
- `SERVICENOW_INSTANCE_URL` - ServiceNow instance URL (e.g., `https://yourfirm.service-now.com`)
- `SERVICENOW_USERNAME` - service account username for API access
- `SERVICENOW_PASSWORD` - service account password (Basic auth) or use OAuth below
- `SERVICENOW_CLIENT_ID` - OAuth 2.0 client ID (if using OAuth instead of Basic auth)
- `SERVICENOW_CLIENT_SECRET` - OAuth 2.0 client secret

## Key operations
- `POST /api/now/table/incident` — create a new incident ticket with category, description, and priority
- `PATCH /api/now/table/incident/{sysId}` — update an incident (status, resolution notes, assignee)
- `GET /api/now/table/incident?sysparm_query=...` — query incidents by requester, status, or category
- `POST /api/now/table/sc_request` — create a service catalog request
- `GET /api/now/table/kb_knowledge?sysparm_query=...` — search knowledge base articles by keyword or category
- `POST /api/now/table/task` — create a follow-up task linked to an incident or request

## Notes
- ServiceNow Basic auth is simplest for service accounts but OAuth is preferred in production for better security and auditability.
- `sys_id` values (GUIDs) are the primary identifiers for all records; retrieve them from search results before updating.
- SLA fields (`sla_due`, `made_sla`) are read-only and managed by ServiceNow automatically based on configured SLA definitions.
- Legal technology incidents (e.g., Relativity, NetDocuments) should use firm-specific category/subcategory values; confirm values with the IT team before creating tickets.
- Avoid bulk-closing tickets via API without human review; incident resolution must meet the firm's defined closure criteria.
