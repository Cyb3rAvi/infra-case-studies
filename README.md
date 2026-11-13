# Infrastructure case studies

Short write-ups of infrastructure projects I worked on as an IT Infrastructure Analyst. Each one follows the same shape: **problem, what I did, the decisions behind it, how it was checked, the result, and what I'd improve.**

> **Confidentiality.** These projects were done for an employer. The write-ups contain no company names, systems, domains, screenshots or data, and no employer code. Scale is described in rounded terms. Diagrams are illustrative, not a map of any real environment.
>
> **How these were built.** I use an AI assistant to help write and review code and documentation. The problem definition, design decisions, safety rules, testing, rollout and results are mine. Where a study describes something I proposed but did not run, it says so.

## Studies

Each study takes about two to three minutes to read.

| # | Project | What it shows | Status |
|---|---------|---------------|--------|
| 1 | [An internal web app that replaced spreadsheets](01-internal-ops-web-app.md) | Building and releasing software safely, access control, Microsoft Graph | In use, being extended |
| 2 | [Automating Azure Front Door certificate renewal with Jenkins](02-azure-front-door-certificate-auto-renewal.md) | Automating a risky recurring task with safe rollout, least privilege and an audit trail | In production |
| 3 | [Permissions cleanup across 500+ SharePoint sites](03-sharepoint-permissions-cleanup.md) | Changing access at scale without causing an outage, audit before acting, reversibility | Completed; some sites held for follow-up |
| 4 | [Certificate-expiry monitoring](04-certificate-expiry-monitoring.md) | Reliability work that prevents incidents before they happen | Running |
| 5 | [Phased BitLocker rollout and compliance tracking](05-bitlocker-rollout.md) | Endpoint security delivered in phases with measurable reporting | Rolled out in phases |
| 6 | [Backup coverage review](06-backup-coverage-review.md) | Finding gaps nobody had listed, and reporting them clearly | Review complete |

## Related

- [infrastructure-automation-toolkit](https://github.com/Cyb3rAvi/infrastructure-automation-toolkit): documented PowerShell for Microsoft 365 and infrastructure admin, written independently and sanitised.

## Adding or updating a study

- Copy [template/study-template.md](template/study-template.md), keep the same headings, and add a row to the table above.
- Keep to what you can show. If there is no number, say so.
- Update the **Status** column and the *Last reviewed* line when a project changes.
- Before publishing, check nothing names the employer, its systems, domains or people.
