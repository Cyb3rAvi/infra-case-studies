# 4. Phased BitLocker rollout and compliance tracking

[← All case studies](README.md)

**Role:** helped roll it out, built the tracking and reporting  ·  **Scale:** several hundred endpoints  ·  **Status:** rolled out in phases

## Problem
Disk encryption was inconsistent across laptops, and there was no reliable view of which devices were encrypted, which were blocked by a hardware or setting problem, and whether a recovery key was stored.

## What I did
- Helped roll BitLocker out in **phases** (a small pilot group first, then wider groups) using device groups, so a problem affected a few devices and not everyone.
- Built **compliance reporting** from the management platform: encryption status per device, and whether a recovery key was stored.
- Followed up the **exceptions** (devices that would not encrypt) and recorded the cause for each.

## Engineering decisions
| Decision | Why |
|---|---|
| Phase by group, pilot first | A bad setting reaches a few devices, not the whole fleet |
| Report per device, not just a total | The exceptions are what need work, and a total hides them |
| Check the recovery key is stored, not only that the disk is encrypted | An encrypted disk with no stored key is a future lockout |

## Risk and validation
Each phase was reviewed through the compliance report before the next one started. The reporting only reads from the management platform.

## Result
- Several hundred devices were brought into a phased rollout with a per-device compliance view.
- Devices that could not encrypt were identified with a cause, instead of being found at the end.

## Limitations
The report shows state at the time it is run; it is not a live dashboard. Hardware that cannot encrypt still needs a separate decision.

## What I'd improve
- Check hardware readiness (Secure Boot, TPM, disk) **before** each phase, to reduce failures during the rollout. A readiness script like the one in the [toolkit](https://github.com/Cyb3rAvi/infrastructure-automation-toolkit) does this.
- Automate the weekly compliance report instead of running it by hand.
