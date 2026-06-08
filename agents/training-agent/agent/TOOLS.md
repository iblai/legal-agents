# Tools — Training & CLE Agent

## CLE Tracking & Compliance

- **Wolters Kluwer Bar Compliance / CLE Passport** — multi-jurisdiction CLE compliance dashboard; credit tracking (hours by type: general, ethics, substance abuse, technology, elimination of bias); jurisdiction-specific requirements; deadline calendar; automatic upload of completion certificates from participating providers.
- **My Bar Insights (ABA)** — bar admission status integration; MCLE requirements by jurisdiction; compliance gap analysis.
- **Videsignate / Compliance Depot (CLE-specific)** — CLE course registry, credit verification, certificate management.

## CLE Content Providers

- **West LegalEdCenter (Thomson Reuters)** — on-demand CLE library; practice-area filtering; accreditation by jurisdiction; transcripts and certificates.
- **PLI (Practising Law Institute)** — intensive programs and on-demand CLE; treatises; practice-specific programs for new associates and specialized practice areas.
- **Lawline** — affordable on-demand CLE library; broad jurisdiction accreditation; specialty tracks.

## Learning Management Systems (LMS)

- **Workday Learning / Cornerstone OnDemand** — firm internal training course enrollment, completion tracking, competency mapping, associate learning plans, mandatory training compliance.
- **LinkedIn Learning** — soft skills and technology training; available by firm subscription.

## Associate Development

- **ViDesignate / Develop by Monash** — associate development plan tracking, competency frameworks, supervisor feedback records, promotion readiness assessments.

## Workspace

- **workspace_write** — save CLE compliance reports, development plan summaries, and training calendars to `/sandbox/.openclaw/workspace/`.

## Data Sources

### CLE Records

- **Bar compliance platform / CLE Passport** — attorney CLE record (bar number, name, jurisdiction(s), current compliance period start/end, hours required by type, hours completed by type, compliance status, next reporting deadline), course completion records (course title, provider, accreditation number by jurisdiction, date completed, credit hours by type, completion certificate reference), credit pending verification (submitted courses awaiting credit approval)
- **Jurisdiction requirements** — jurisdiction (state/territory), compliance period length, annual vs. biennial reporting, hours required (total, ethics, substance abuse, technology, elimination of bias, other specialty), late filing rules, grace period, exemptions (newly admitted, judicial clerks, senior attorneys)

### Internal Training

- **LMS (Workday / Cornerstone)** — training records (employee ID, course name, course category, assigned date, completed date, score if assessed, certificate), learning plans (plan ID, employee, development goal, assigned courses, target completion date, status), mandatory training compliance (training name, due date, completion status, escalation status)

### Associate Development

- **Development plans** — associate ID, supervising partner, development goals by competency (legal skills, client service, business development, leadership), training assignments, mentorship pairings, mid-year and year-end review dates, promotion timeline
- **Competency frameworks** — level (associate year 1-8, counsel, partner), competency name, behavioral indicators, assessment criteria, development resources

### CLE Content Library

- **Provider catalog** — provider name, accreditation jurisdictions, course titles, credit hours by type, format (live/on-demand/in-person), cost, relevance tags by practice area
