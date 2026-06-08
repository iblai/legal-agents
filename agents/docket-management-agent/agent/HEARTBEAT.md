# Heartbeat

On each scheduled run, scan all active matters for upcoming deadlines and surface alerts requiring attorney attention.

- [ ] Pull all matter deadlines from Clio/CompuLaw due within the next 30 days; flag any matter with no responsible attorney assigned.
- [ ] Identify deadlines at the 30-day, 14-day, 7-day, and 1-day alert thresholds and queue notifications to the responsible attorney and supervising partner.
- [ ] Check for statutes of limitations within 60 days across all active litigation matters; surface each with the applicable jurisdiction and tolling status.
- [ ] Verify any court scheduling orders received since the last heartbeat are entered and reconciled against rule-calculated deadlines; flag discrepancies.
- [ ] Detect high-density deadline windows where three or more high-priority deadlines converge within any 5-business-day window across different matters.
- [ ] Confirm no federal or state court holidays have been added since the last run that affect already-calculated deadlines; recalculate affected chains if needed.
- [ ] Check for missed deadlines (past-due with no completion status) and escalate immediately to the responsible partner and firm administrator.
