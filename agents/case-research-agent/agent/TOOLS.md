# Tools — Case Research Agent

## Legal Research Platforms

- **Westlaw (Thomson Reuters)** — primary case law and statutory research; supports natural-language and Boolean queries; KeyCite for citation status (red/yellow flags, depth of treatment, citing references); Key Number System for issue classification; secondary sources (Am. Jur., C.J.S., practice guides, law reviews).
- **Lexis+ (LexisNexis)** — case law, statutes, regulations, and secondary sources; Shepard's Citations for treatment history and validity; Search Term Map for query refinement; Lexis Answers for point-in-time statutory text.
- **Fastcase** — alternative research platform; Authority Check for citation validation; Interactive Citation Map; good for state-specific and administrative law coverage.
- **Casetext / CoCounsel** — AI-assisted legal research and document review; Brief Analyzer for identifying relevant precedent against an uploaded brief; parallel citation search.
- **CourtListener / PACER (via integration)** — federal docket searches, PACER filings, opinions from RECAP archive; free primary source verification.
- **vLex** — international and comparative law research; treaties, foreign case law, and cross-border regulatory analysis.

## Secondary Sources & Treatises

- **Bloomberg Law** — transactional and litigation practice guides, draft analyzer, Points of Law extraction from opinions.
- **HeinOnline** — full law review archive, federal register, U.S. treaties, session laws.

## Workspace

- **workspace_write** — save research memos, citation lists, and annotated summaries to `/sandbox/.openclaw/workspace/` for consumption by `brief-drafting-agent` or `knowledge-agent`.

## Data Sources

### Primary Legal Databases

- **Westlaw** — case opinions (citation, court, date decided, full text, headnotes, Key Numbers, treatment flags), statutes (current and historical text, annotations, session law history), regulations (CFR, Federal Register, state administrative codes), KeyCite history (citing references, depth of treatment, negative treatment flags, headnote-level treatment)
- **Lexis+** — case law (citation, syllabus, headnotes, full opinion, Shepard's signal), annotated codes (federal and all 50 states, Puerto Rico, territories), secondary sources (law reviews, practice guides, form books), Shepard's citations (citing sources, treatment phrases, headnote history, history type)
- **Fastcase** — case text (court, citation, date, full opinion), Authority Check results (citing cases, treatment type, count), citation map (visual relationship graph between cases)
- **CourtListener / RECAP** — federal opinions (court, docket number, case name, date filed, date decided, full text, download URL), PACER docket entries (entry number, date, description, document links), party and attorney information

### Regulatory Sources

- **GovInfo (GPO)** — Code of Federal Regulations (title, part, section, effective date, full text), Federal Register (volume, issue date, document type, agency, full text), U.S. Code (title, chapter, section, notes of decisions)
- **State legislative portals** — enrolled bills, session laws, codified statutes, legislative history documents (committee reports, floor amendments, fiscal notes)

### Secondary Sources

- **HeinOnline** — law review articles (journal, volume, issue, page, author, abstract, full text), treaty texts, AG opinions, state session laws
- **Bloomberg Law** — practice guides (chapter, section, last updated date), Points of Law (principle, supporting cases, opposing cases)
