<div align="center">

<a href="https://ibl.ai"><img src="https://ibl.ai/images/iblai-logo.png" alt="ibl.ai" width="300"></a>

# Legal Agents

Drop-in [OpenClaw](https://github.com/iblai/iblai-claw-setup) / [NemoClaw](https://github.com/NVIDIA/NemoClaw) agent configuration for the [ibl.ai](https://ibl.ai) **Legal** solution segment — one Firm Assistant orchestrator plus 12 specialist subagents, packaged so a NemoClaw host can import the whole roster with zero conversion.

[![OpenClaw](https://img.shields.io/badge/OpenClaw-292929?logoColor=white)](https://github.com/iblai/iblai-claw-setup)
[![NemoClaw](https://img.shields.io/badge/NemoClaw-76B900?logo=nvidia&logoColor=white)](https://github.com/NVIDIA/NemoClaw)
[![ibl.ai Platform](https://img.shields.io/badge/ibl.ai_Platform-4A90D9?logoColor=white)](https://ibl.ai)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-blue.svg)](#license)

</div>

---

This directory is a complete, drop-in NemoClaw/OpenClaw configuration for the **Legal** solution segment. It defines one parent orchestration agent and twelve specialist subagents covering the full operational surface of a law firm.

Copy the contents of this directory into `/sandbox/.openclaw/` on a NemoClaw sandbox and the configuration is ready to load — no conversion required.

---

## Agent Roster

| ID | Name | Role |
|---|---|---|
| `legal-assistant` | Firm Assistant | **Parent** — segment entry point; interprets intent and delegates to specialist subagents |
| `case-research-agent` | Case Research | Legal research and case law analysis |
| `contract-review-agent` | Contract Review | Agreement analysis and risk flagging |
| `client-intake-agent` | Client Intake | New matter opening and conflict-cleared client onboarding |
| `billing-time-agent` | Billing & Time | Time entry and invoice management |
| `discovery-agent` | Discovery | Document review and production |
| `compliance-agent` | Compliance | Ethics rules and regulatory compliance |
| `knowledge-agent` | Knowledge Base | Firm precedent and institutional memory |
| `brief-drafting-agent` | Brief Drafting | Motion and brief preparation |
| `conflicts-check-agent` | Conflicts Check | Pre-engagement conflict screening |
| `training-agent` | Training & CLE | CLE tracking and associate development |
| `docket-management-agent` | Docket Management | Deadline tracking and calendar management |
| `it-help-desk-agent` | IT Help Desk | Technical support and system access |

---

## How It Works

The **Firm Assistant** (`legal-assistant`) is the default entry point. When an attorney, paralegal, or staff member sends a message, the Firm Assistant:

1. Identifies the intent (research, drafting, intake, billing, discovery, compliance, knowledge, conflicts, training, docketing, or IT).
2. Spawns the appropriate specialist subagent via `sessions_spawn`.
3. Waits for the subagent result.
4. Synthesizes and returns a clear, actionable response.

For multi-domain requests (e.g., opening a new matter requires a conflicts check before intake), the Firm Assistant orchestrates subagents in the correct sequence. Conflicts check always runs before client intake.

---

## Import Instructions

Follow these steps to deploy this configuration on a NemoClaw sandbox.

**1. Copy the directory contents.**

```bash
git clone https://github.com/iblai/legal-agents.git
cp -r legal-agents/. /sandbox/.openclaw/
cp legal/.env.example /sandbox/.openclaw/
```

Ensure the directory structure is preserved. The result should be:

```
/sandbox/.openclaw/
├── openclaw.json
├── .config-hash
├── .env.example
├── workspace/
│   └── .gitkeep
├── skills/
│   ├── clio/SKILL.md
│   ├── docket-alarm/SKILL.md
│   ├── docusign/SKILL.md
│   ├── imanage/SKILL.md
│   ├── intapp-conflicts/SKILL.md
│   ├── ironclad/SKILL.md
│   ├── netdocuments/SKILL.md
│   ├── pacer/SKILL.md
│   ├── relativity/SKILL.md
│   ├── servicenow/SKILL.md
│   └── westlaw/SKILL.md
└── agents/
    ├── legal-assistant/agent/
    ├── case-research-agent/agent/
    ├── contract-review-agent/agent/
    ├── client-intake-agent/agent/
    ├── billing-time-agent/agent/
    ├── discovery-agent/agent/
    ├── compliance-agent/agent/
    ├── knowledge-agent/agent/
    ├── brief-drafting-agent/agent/
    ├── conflicts-check-agent/agent/
    ├── training-agent/agent/
    ├── docket-management-agent/agent/
    └── it-help-desk-agent/agent/
```

Each agent directory contains the following workspace files:

| File | Required | Purpose |
|---|---|---|
| `IDENTITY.md` | Yes | Agent persona: Name, Role, Vibe |
| `SOUL.md` | Yes | Behavioral guidelines and boundaries |
| `TOOLS.md` | Yes | Available integrations, data sources, and platform data fields |
| `auth-profiles.json` | Yes | Inference credential profile |
| `AGENTS.md` | Parent only | Subagent roster and delegation rules |
| `USER.md` | As needed | User or environment-specific context |
| `BOOTSTRAP.md` | As needed | One-time first-run setup actions (consumed after use) |
| `HEARTBEAT.md` | As needed | Periodic monitoring checklist for proactive agents |
| `MEMORY.md` | As needed | Seed long-term facts for rules-heavy agents |

**2. Set ownership.**

```bash
chown -R sandbox:sandbox /sandbox/.openclaw/
```

**3. Set up credentials.**

Two credential sources must be populated before the agents can call external platforms.

*Inference credentials* — every `auth-profiles.json` contains a non-functional placeholder API key. Replace the `apiKey` value in each file with a real Anthropic API key (or the appropriate credential for your inference provider):

```bash
find /sandbox/.openclaw/agents -name auth-profiles.json
```

Edit each file and replace the value of `"apiKey"` under `profiles.anthropic`.

*Tool credentials* — `.env.example` is a committed sample template representing the OpenClaw daemon env file `~/.openclaw/.env`. It contains non-functional placeholder values for every third-party platform used by the segment. Copy it and fill in real credentials:

```bash
cp /sandbox/.openclaw/.env.example ~/.openclaw/.env
# then edit ~/.openclaw/.env and replace every SAMPLE-... value
```

`.env.example` is safe to commit; `~/.openclaw/.env` (with real keys) must never be committed.

**4. Recompute the config hash.**

After any edit to `openclaw.json` (including none), recompute the hash:

```bash
cd /sandbox/.openclaw
sha256sum openclaw.json > .config-hash
```

On macOS use `shasum -a 256` instead of `sha256sum`.

**5. Reload the OpenClaw gateway.**

```bash
openclaw reload
# or restart the NemoClaw service via your host's service manager
```

---

## Tool Skills

The `skills/` directory contains one subdirectory per third-party platform, each containing a `SKILL.md` file. Each skill describes the platform's capabilities, the specific API operations, authentication patterns, and declares required env vars in its frontmatter `metadata` key. Agents load the relevant skill files at runtime to understand how to call external systems.

All skills draw credentials from `~/.openclaw/.env` on the daemon host. The committed sample template `.env.example` contains non-functional placeholder values for every platform; copy it to `~/.openclaw/.env` and replace each placeholder with a real credential before deploying (see Import Instructions, step 3).

| Directory | Description |
|---|---|
| `clio/` | Clio Manage/Grow practice management platform; lets an agent create matters, log time, generate invoices, manage client intake, and sync docket deadlines. |
| `docket-alarm/` | Docket Alarm court monitoring and analytics platform; lets an agent track docket updates, set filing alerts, and pull judge analytics for motion strategy. |
| `docusign/` | DocuSign e-signature platform; lets an agent send engagement letters and contracts for signature, track envelope status, and retrieve executed documents. |
| `imanage/` | iManage Work matter-centric DMS; lets an agent retrieve, file, and version legal work product organized by client and matter workspace. |
| `intapp-conflicts/` | Intapp Conflicts firm-wide conflicts management system; lets an agent run new-business conflict searches, retrieve hit reports, and track waiver records. |
| `ironclad/` | Ironclad contract lifecycle management (CLM) platform; lets an agent upload contracts, run playbook analysis, retrieve risk scores, and track obligations and approvals. |
| `netdocuments/` | NetDocuments cloud DMS; lets an agent store, retrieve, version, and search matter documents including briefs, contracts, and precedents. |
| `pacer/` | PACER/CM-ECF federal court system; lets an agent retrieve docket entries, case schedules, local rules, filed documents, and scheduling orders for federal matters. |
| `relativity/` | Relativity e-discovery platform; lets an agent manage review workspaces, run searches, track coding decisions, and generate privilege logs and production sets. |
| `servicenow/` | ServiceNow ITSM platform; lets an agent create, update, and resolve IT incident and service request tickets and retrieve knowledge base articles. |
| `westlaw/` | Westlaw (Thomson Reuters) legal research platform; lets an agent search case law, statutes, regulations, and validate citations via KeyCite. |

---

## Notes

- The parent agent (`legal-assistant`) is marked `"default": true` and will be the first agent users interact with.
- All agents use `anthropic/claude-sonnet-4-5-20250929` by default. To change the model, update `openclaw.json` and recompute the config hash.
- The shared workspace at `/sandbox/.openclaw/workspace/` is writable by all agents and is used to pass structured context between subagents within a session.
- Agents do not give legal advice. They assist qualified legal professionals. All outputs requiring professional judgment must be reviewed and approved by a licensed attorney.

---

## License

Proprietary — ibl.ai
