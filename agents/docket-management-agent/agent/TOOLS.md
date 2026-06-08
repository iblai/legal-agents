# Tools — Docket Management Agent

## Docketing & Calendar Services

- **CompuLaw / Deadlines.com** — rules-based deadline calculation engine; jurisdiction-specific civil procedure rules (FRCP, state civil rules, appellate rules); automatic deadline chains from trigger events (filing date, service date, notice date); court holiday integration; customizable alert schedules.
- **Docket Alarm** — federal and state court docket monitoring; automatic docket alerts; PACER integration; judge analytics; hearing schedule retrieval.
- **CourtAlert** — real-time court docket monitoring, new filing alerts, hearing notices, order alerts by matter.

## Practice Management Calendar Integration

- **Clio Manage** — matter deadline calendar (create, update, delete calendar entries); recurring reminder setup; attorney and paralegal calendar assignment; calendar sync with Outlook/Google Calendar.
- **MyCase / Filevine** — matter task and deadline management; milestone tracking; calendar integration.

## Court Systems

- **PACER / CM/ECF** — federal court docket retrieval; scheduling order access; case status verification; filed document retrieval.
- **State court electronic filing portals** — state-specific case status, hearing schedules, and scheduling order retrieval.

## Statute of Limitations Reference

- **Westlaw / Lexis+** — SOL rules by jurisdiction and cause of action; tolling doctrines; discovery rule applications; statutes of repose.

## Workspace

- **workspace_write** — save deadline reports, upcoming-deadline summaries, and matter calendar exports to `/sandbox/.openclaw/workspace/` for attorney review.

## Data Sources

### Matter Deadlines & Calendar

- **Practice management (Clio / MyCase / Filevine)** — deadline records (deadline ID, matter number, deadline type, deadline date, created from rule, trigger event, trigger date, assigned attorney/paralegal, status: open/completed/waived, reminder schedule), task records (task ID, matter number, description, assigned to, due date, priority, status), hearing records (hearing ID, matter number, court, judge, hearing type, date/time, location, preparation tasks)
- **Scheduling order entries** — matter number, court, scheduling order date, key dates (discovery cutoff, expert disclosure, dispositive motion, pretrial conference, trial), source document reference

### Court Docket Data

- **PACER / Docket Alarm** — docket entries (docket number, entry date, entry text, document links, filer), case schedule (hearing type, date, time, location, judge), case status (open/closed, case type, assigned judge, filing date)
- **State court portals** — case number, court, judge, case type, filing date, status, upcoming events list

### Deadline Calculation Rules

- **CompuLaw / Deadlines.com rules engine** — rule set (jurisdiction, court type, rule name, trigger event, calculation method: calendar days/business days/court days, count from: filing/service/notice, holiday calendar, exceptions), computed deadline (trigger date, rule applied, computed date, attorney-verified flag)

### Statutes of Limitations Reference

- **SOL database** — jurisdiction, cause of action, limitations period, accrual rule, tolling provisions, discovery rule applicability, statute of repose if any, last confirmed date
