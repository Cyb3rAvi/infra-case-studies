# 4. Certificate-expiry monitoring

[← All case studies](README.md)

**Role:** built and maintain it  ·  **Scale:** around 60 endpoints  ·  **Status:** running
**Skills:** PowerShell · scheduled jobs · TLS certificates · Entra application credentials · email alerting  ·  **Reading time:** about 2 minutes

## Problem
TLS certificates and application credentials expired without warning, because expiry dates were tracked in people's heads and spreadsheets. An expired certificate is a preventable outage.

## What I built
- A **maintained list of endpoints** to watch, treated as the single source of truth.
- A **scheduled check** that reads each endpoint's certificate, works out the days to expiry and emails a list of what is expiring soon.
- A second check for **expiring or expired credentials on directory applications**, with a review list of the ones that are no longer used.
- A short note on how to add an endpoint and how to renew.

## Engineering decisions
| Decision | Why |
|---|---|
| One maintained endpoint list, kept on the server | One source of truth, instead of several spreadsheets that disagree |
| Check the live certificate, not a stored expiry date | Catches a renewed or replaced certificate, and an unexpected one |
| Cover directory application credentials as well as web certificates | Expired app credentials break integrations just as quietly |

## Risk and validation
The email report was compared against the endpoint list to make sure every listed endpoint was checked. The check only reads certificates; it changes nothing.

## Result
- Around 60 endpoints are checked on a schedule, with an emailed report of what is close to expiry.
- Application credentials were reviewed, and a list of unused ones was prepared for cleanup. The cleanup itself is waiting for approval.

## Limitations
The alert goes to one mailbox. It only knows about endpoints that are on the list, so a new one has to be added by hand.

## What I'd improve
- Send alerts to a shared mailbox or channel, so it survives staff changes.
- Feed the same list into the existing monitoring tool so there is one alerting path.
- Record who owns each certificate, not just when it expires.

*Last reviewed: November 2026*
