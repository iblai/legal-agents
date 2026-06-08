# Tools — Discovery Agent

## E-Discovery Platforms

- **Relativity** — document review workspace management, review coding (responsive, privilege, hot docs), saved searches, search term reports, conceptual clustering, TAR/CAL (technology-assisted review) workflow management, production set creation, load file generation (DAT/OPT), privilege log export.
- **Everlaw** — document review, prediction-assisted review, storybuilding, deposition preparation, binder creation, timeline analysis, production and export.
- **DISCO** — AI-powered review, search, automated issue coding, privilege detection, deposition summaries, production management.
- **Logikcull** — self-service ESI processing and review; custodian-based upload, search term filtering, hold notice management, production download.
- **Nuix Workstation** — high-volume ESI processing; metadata extraction, deduplication, near-dedup, language detection, OCR, and export to review platform load files.

## Litigation Hold

- **ZL Technologies / Onna / Hanzo** — litigation hold notice issuance and tracking, custodian acknowledgment status, data preservation verification, hold escalation.

## Document Management

- **NetDocuments / iManage** — production document retrieval, matter document sets, custodian file organization, privilege log document linking.

## Workspace

- **workspace_write** — save privilege logs, review coding summaries, production manifests, and hold status reports to `/sandbox/.openclaw/workspace/`.

## Data Sources

### ESI Processing & Review

- **Relativity** — document records (document ID, custodian, date, file type, file size, MD5 hash, deduplication status, review status, coding decisions: responsive/non-responsive/privilege/hot), search results (search name, hit count, document list), production sets (set name, document count, Bates range, export format, production date), privilege log (document ID, Bates number, date, author, recipients, privilege type, description)
- **Everlaw / DISCO / Logikcull** — equivalent document, review, and production fields; TAR/predictive coding scores (document ID, prediction score, seed set status, review round), issue tags (tag name, tag count, tagged documents)

### Litigation Hold

- **Hold management platform** — hold notice records (hold ID, matter number, issued date, issued by, custodian list, data sources in scope, acknowledgment deadline), custodian acknowledgments (custodian name, email, acknowledged date, response status), preservation verification (source system, preservation method, confirmed date, data volume)

### Collections & Metadata

- **Collection records** — collection ID, custodian, collection date, data source (email, file share, cloud storage, mobile), volume (GB), collection method, chain-of-custody log entries
- **Document metadata** — file name, full path, custodian, created date, modified date, author, email fields (from, to, CC, BCC, subject, sent date, thread ID), attachment relationships, deduplication family groupings

### Productions

- **Production log** — production ID, requesting party, response date, Bates range, document count, format (native/TIFF/PDF), load file type, production volume, transmittal letter reference, protective order designation
