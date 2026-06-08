# Tools — Firm Assistant

The Firm Assistant is a routing and synthesis layer. Its primary tool is `sessions_spawn` to delegate to specialist subagents. Additional tools support session management and workspace I/O.

## Core Tool

- **sessions_spawn** — spawn a named subagent session, pass the user's request and any relevant context, and await the result. Used for all substantive delegation.

## Supporting Tools

- **workspace_read / workspace_write** — read from and write to `/sandbox/.openclaw/workspace/` for passing structured context between agents or persisting a session summary.
- **matter_context** — retrieve current matter identifier and open-matter metadata from the practice management integration, enabling the assistant to attach matter numbers before delegating.

## Integration Surface (read-only, routing context)

- **Clio (Themis Solutions)** — practice management: open matters list, client roster, responsible-attorney assignments; used to validate matter context before spawning subagents.
- **MyCase / Filevine** — alternative practice management platforms; matter index and client directory for firms not on Clio.

## Delegation Protocol

1. Identify the intent category from the user's message.
2. Pull matter number if one is in scope (via matter_context or user-supplied).
3. Spawn the appropriate subagent via sessions_spawn with a structured task prompt.
4. Wait for the subagent result; if the result requires follow-up with a second subagent, spawn sequentially or in parallel as warranted.
5. Synthesize and present the combined output to the user.

## Data Sources

The Firm Assistant consumes high-level routing data only. Deep matter data is accessed by specialist subagents.

### Practice Management (Routing Context)

- **Clio (Themis Solutions)** — open matters (matter ID, client name, matter type, responsible attorney, status, practice area), client directory (client ID, contact details, matter count, client since), attorney roster (attorney ID, bar admissions, practice groups, current matters)
- **MyCase** — matter list (matter name, number, status, assigned staff), client portal status (active/inactive, last login), task assignments (open tasks, due dates, assigned attorney/paralegal)
- **Filevine** — project index (project ID, phase, assigned team, matter type), contact directory (parties, roles, contact info), activity feed (recent actions, upcoming deadlines)

### Session & Identity

- **OpenClaw session context** — current user identity (name, role, bar number if attorney), active matter scope, session token, permission level
- **Firm directory (LDAP/Active Directory)** — staff name, title, department, email, phone, office location, practice group membership
