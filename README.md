# Infrastructure case studies

Short write-ups of infrastructure projects I worked on as an IT Infrastructure Analyst. Each one follows the same shape: **problem, what I did, the decisions behind it, how it was checked, the result, and what I'd improve.**

> **Confidentiality.** These projects were done for an employer. The write-ups contain no company names, systems, domains, screenshots or data, and no employer code. Scale is described in rounded terms. Diagrams are illustrative, not a map of any real environment.
>
> **How these were built.** I use an AI assistant to help write and review code and documentation. The problem definition, design decisions, safety rules, testing, rollout and results are mine. Where a study describes something I proposed but did not run, it says so.

## Studies

| # | Project | What it shows |
|---|---------|---------------|
| 1 | [An internal web app that replaced spreadsheets](01-internal-ops-web-app.md) | Building and releasing software safely, access control, Microsoft Graph |
| 2 | [Automating Azure Front Door certificate renewal with Jenkins](02-azure-front-door-certificate-auto-renewal.md) | Automating a risky recurring task with safe rollout, least privilege and an audit trail |
| 3 | [Permissions cleanup across 500+ SharePoint sites](03-sharepoint-permissions-cleanup.md) | Changing access at scale without causing an outage, audit before acting, reversibility |
| 4 | [Certificate-expiry monitoring](04-certificate-expiry-monitoring.md) | Reliability work that prevents incidents before they happen |
| 5 | [Phased BitLocker rollout and compliance tracking](05-bitlocker-rollout.md) | Endpoint security delivered in phases with measurable reporting |
| 6 | [Backup coverage review](06-backup-coverage-review.md) | Finding gaps nobody had listed, and reporting them clearly |

## Related

- [infrastructure-automation-toolkit](https://github.com/Cyb3rAvi/infrastructure-automation-toolkit): documented PowerShell for Microsoft 365 and infrastructure admin, written independently and sanitised.
