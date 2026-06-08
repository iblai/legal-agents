# Tools — Conflicts Check Agent

## Conflicts Management Systems

- **Intapp Conflicts** — firm-wide conflicts database; new-business intake search (party name, entity hierarchy, matter type, opposing counsel, adverse parties); hit analysis (exact match, phonetic match, AKA match, related-entity match); waiver management; matter relationship mapping.
- **Clio Conflicts** — built-in conflicts search across all clients and matters; party name search; adverse party tracking; conflict report generation.
- **Aderant Expert / Elite** — large-firm conflicts management; Boolean and fuzzy search across client, matter, and party databases; lateral integration; ethical screen management.

## Entity Research

- **Dun & Bradstreet (D&B) / LexisNexis Corporate Affiliations** — corporate entity hierarchy lookup; parent, subsidiary, and affiliate identification; trade name and DBA search; helps ensure the full entity tree is checked.
- **OpenCorporates / Secretary of State portals** — registered agent, principal, and corporate officer lookup for entity verification.

## Sanctions & Adverse Party Screening

- **Dow Jones Risk & Compliance** — OFAC SDN list, EU consolidated list, UN sanctions list, PEP (politically exposed persons) screening; adverse media screening.
- **LexisNexis Bridger Insight** — sanctions and watchlist screening; adverse media; global PEP database.

## Waiver Tracking

- **Waiver register (internal)** — conflicts waiver records (waiver ID, matter, conflicted party, waiving client(s), waiver date, waiver scope, signed waiver document location, expiration if applicable).

## Workspace

- **workspace_write** — save the full conflicts search report (search terms, hits, dispositions, cleared-by, cleared-date) to `/sandbox/.openclaw/workspace/` for the conflicts file.

## Data Sources

### Conflicts Database

- **Intapp Conflicts / Clio / Aderant** — client records (client ID, legal name, trade names/DBAs, entity type, jurisdiction of formation, parent entity, key principals), matter records (matter ID, client ID, matter type, adverse parties, opposing counsel and firm, status: open/closed), adverse party database (party name, matter number(s), party role, last updated), party relationship graph (entity hierarchy, affiliate links, related-matter links)
- **Lateral arrival records** — attorney name, prior firm, all prior matters (anonymized list with adverse parties, matter types, dates), screens established, conflicts identified

### Waiver Records

- **Waiver register** — waiver ID, conflicted matter, conflicted party name, waiving client(s) (name, signature, date), waiver scope (matter-specific or matter-type), obtaining attorney, waiver document location, expiration date if any, subsequent matter applicability notes

### Entity & Corporate Structure

- **D&B / LexisNexis Corporate Affiliations** — entity name, DUNS number, parent entity, ultimate parent, subsidiary list, trade names, registered address, jurisdiction, active/inactive status
- **Secretary of State records** — registered agent name and address, principal officer names, formation date, status

### Sanctions & PEP Screening

- **OFAC SDN / EU / UN sanctions** — screened name, list(s) searched, search date, result (clear/potential match/confirmed match), match details (name, list, SDN number, basis), disposition (cleared/escalated/declined)
- **Adverse media** — screening subject, search date, media hits (publication, date, headline, summary), risk classification
