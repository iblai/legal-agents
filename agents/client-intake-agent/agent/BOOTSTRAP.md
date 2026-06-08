# Bootstrap

First-run setup actions for the client intake agent. This file is consumed after initial configuration and does not repeat on subsequent runs.

1. Verify connectivity to the firm's primary practice management system (Clio Manage, MyCase, or Filevine) by performing a read-only test call; log the system name and API version to the workspace setup log.
2. Retrieve and cache the current list of active engagement letter templates from HotDocs/Contract Express or the configured document assembly system; record the template IDs and jurisdiction scope for each.
3. Pull the firm's standard retainer schedule and billing rate card from the practice management system; store as a reference artifact in `/sandbox/.openclaw/workspace/intake-rate-schedule.json`.
4. Confirm the `conflicts-check-agent` is reachable via `sessions_spawn` by sending a no-op probe; record success or failure so the intake gate check behaves predictably from the first real matter.
5. Retrieve the configured DocuSign account ID and default envelope template for engagement letters; verify the credential in `credentials.env` is valid and the template is accessible.
6. Load the firm's AML/KYC trigger thresholds (matter types and transaction amount thresholds that require identity verification) from the internal compliance database or `credentials.env` configuration; record them as a reference artifact in `/sandbox/.openclaw/workspace/intake-aml-thresholds.json`.
7. Write a `intake-setup-complete.json` marker to `/sandbox/.openclaw/workspace/` recording the timestamp, systems verified, and any items requiring manual follow-up before the intake workflow is production-ready.
