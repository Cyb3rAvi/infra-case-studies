# 6. Backup coverage review

[← All case studies](README.md)

**Role:** carried out the review and produced the report  ·  **Scale:** virtual machines across cloud and on-premises  ·  **Status:** review complete; follow-up decisions pending
**Skills:** Azure · Hyper-V · backup reporting · Excel reporting  ·  **Reading time:** about 2 minutes

## Problem
Backups existed, but nobody had a single list of which virtual machines were protected, which were not, and which backups were stale. The question "is everything backed up?" could not be answered.

## What I did
- Listed every virtual machine across the **cloud and on-premises** environments and matched each one against its backup protection.
- Sorted them into **protected, not protected, stopped (possibly left unbacked up on purpose), and protected but stale** (last successful backup too old).
- Produced a **workbook** with the gaps and the reasons, so a decision could be made for each.

## Engineering decisions
| Decision | Why |
|---|---|
| Start from the list of machines, not the list of backups | A machine with no backup never appears in a backup report |
| Separate "stopped" from "unprotected" | A stopped machine may be deliberately unprotected; it needs a question, not an alarm |
| Treat "stale" as its own category | A backup that exists but has not run recently gives false comfort |

## Risk and validation
The review only read from the cloud and backup platforms; it changed nothing.

## Result
- A complete list of machines against their protection, including a set of unprotected machines and a set with stale backups, each with a reason.
- The gaps are reported; deciding what to protect and what to retire is the follow-up.

## Limitations
This is a point-in-time review, not continuous monitoring. It does not judge whether a backup can be restored.

## What I'd improve
- Make the comparison a scheduled report, so a new machine without backup is caught within days.
- Agree up front what "protected" means (frequency and retention), so the list is judged against a clear standard.
- Add a periodic restore test.

*Last reviewed: November 2026*
