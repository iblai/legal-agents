# Tools — Knowledge Base Agent

## Document Management Systems

- **NetDocuments** — full-text and metadata search across matter documents; filter by practice area, document type, author, date range; retrieve versioned documents; access clause libraries stored in firm profiles.
- **iManage Work** — matter-centric document search; knowledge management workspace (KM profiles), work product retrieval by document type and practice area, prior deal comparables, briefing notes.
- **Litera Transact / Clause Advisor** — standard clause library retrieval and comparison; approved fallback language by contract type; clause version history and approval trail.

## Knowledge Management Platforms

- **Foundation IP / Innodex** — patent and IP precedent retrieval for IP practice groups; prior prosecution history, licensing agreement templates, IP portfolio summaries.
- **Practical Law (Thomson Reuters)** — standard forms, practice notes, checklists, and "what's market" data for transactional matters; legal updates by practice area.
- **Bloomberg Law Drafting Assistant** — clause suggestions, market standard comparisons, and prior firm drafting patterns for transactional documents.

## Internal Wikis & Playbooks

- **Confluence / SharePoint** — firm internal wiki search; practice group playbooks, client secondment guides, deal process checklists, training materials, policy documents.

## Workspace

- **workspace_read / workspace_write** — retrieve prior session research deposited by `case-research-agent` or `brief-drafting-agent`; save knowledge retrieval summaries for use by other agents.

## Data Sources

### Document Management & Work Product

- **NetDocuments / iManage** — document records (document ID, matter number, practice area, document type, title, author, created date, last modified, version, status, profile fields), full-text index (searchable content, keyword hits, relevance score), folder/workspace structure (practice area workspace, matter folder, document type subfolder)
- **Precedent library** — form ID, document type, practice area, jurisdiction, last reviewed date, reviewing attorney, version notes, associated playbook, approved-for-use flag

### Clause & Form Libraries

- **Litera / Practical Law** — clause library (clause ID, clause type, contract type, approved text, fallback text, risk rating, last reviewed date, jurisdiction variants), standard form library (form name, version, practice area, jurisdiction, last updated, originating attorney)
- **Market standard data** — provision type, market standard position, frequency of use (market data source, date of survey, deal type, deal size range)

### Playbooks & Internal Guides

- **Confluence / SharePoint** — page title, practice group, last edited, page content (procedure, checklist, decision tree, policy), related documents, version history
- **Deal database** — matter number (anonymized), deal type, deal size, jurisdiction, governing law, closing date, key terms, standard deviations from firm form, outcome notes

### Knowledge Gaps

- **Unresolved query log** — query text, date, requesting attorney, practice area, resolution status (answered/escalated/unresolved), response summary if resolved
