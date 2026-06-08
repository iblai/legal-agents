# Tools — Brief Drafting Agent

## Drafting & Editing

- **Litera Draft / Draftwise** — in-document drafting assistance, clause suggestions drawn from firm precedents, style and consistency checks, defined-terms cross-reference validation.
- **Westlaw Drafting Assistant** — jurisdiction-specific form library, local rules integration, plain-language guidance, suggested language drawn from court opinions.
- **Bloomberg Law Draft Analyzer** — cite-checking against Bloomberg database, brief scoring, argument gap analysis.

## Document Management

- **NetDocuments / iManage** — save and version draft briefs, retrieve related matter documents, prior briefs on the same legal theory, and court opinions attached to the matter.

## Citation & Shepardizing

- **Westlaw KeyCite** — verify citation validity and treatment before including in a brief; flag any red or yellow flags.
- **Lexis+ Shepard's** — parallel citation checking; confirm positive treatment and identify distinguishing cases.

## Court Rules & Local Rules

- **PACER / CM/ECF** — retrieve local rules, standing orders, judge-specific preferences, and scheduling orders for the filing court.
- **CourtAlert / Docket Alarm** — court rule lookups, judge filing statistics, and motion-practice analytics for argument strategy.

## Workspace

- **workspace_read** — pull research memos from `case-research-agent` and clause precedents from `knowledge-agent` into the drafting context.
- **workspace_write** — save completed draft briefs and memos to `/sandbox/.openclaw/workspace/` for attorney review and DMS filing.

## Data Sources

### Prior Briefs & Pleadings

- **DMS (NetDocuments / iManage)** — prior filings by matter (document ID, matter number, court, filing type, filed date, attorney author, version history), motion practice history (motions filed, outcomes, court's reasoning from orders), form briefs and templates (template ID, court, motion type, jurisdiction, last updated)

### Court Rules & Procedures

- **PACER / CM/ECF** — local civil rules (rule number, court, last amended date, full text), standing orders (judge name, order date, subject, full text), scheduling order (matter-specific deadlines: discovery cutoff, dispositive motion deadline, pretrial conference, trial date), page limits and formatting requirements by court and motion type
- **State court portals** — state court rules (civil, criminal, appellate), court-specific electronic filing requirements, mandatory forms

### Legal Research (from workspace)

- **case-research-agent outputs** — research memos (issue, controlling authority, favorable cases, adverse cases, citation list), shepardized citation list, statutory text
- **knowledge-agent outputs** — prior firm briefs on same legal theory, standard argument blocks, prior favorable orders

### Argument Analysis

- **Docket Alarm / CourtAlert** — judge analytics (motion grant rates, preferred argument styles, citation preferences, average time to ruling), attorney-before-judge history, similar motion outcomes in the same court
