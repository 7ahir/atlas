# Incident Review: Self-Hosted Upgrade Failure — v3.14 → v3.15

## Summary

A self-hosted upgrade from v3.14 to v3.15 failed across 11 enterprise customers during a
3-hour window. Affected customers experienced degraded tenant provisioning and intermittent
authentication failures. Four customers required rollback. No data loss occurred.

| Field | Detail |
|---|---|
| Date | Week 6 of Q1 |
| Duration | 3h 20m degraded, 45m to full recovery for rolling customers |
| Affected customers | 11 (7 degraded, 4 rolled back) |
| Surfaces affected | Self-hosted deployment layer, SaaS operations control plane |
| Severity | P1 (customer-impacting, multiple accounts) |
| Incident owner | Platform SRE lead |
| PM on incident | Platform PM |

## Timeline

| Time | Event |
|---|---|
| T+0 | First customer reports authentication errors post-upgrade via support |
| T+12m | Platform SRE begins investigation; two additional reports received |
| T+28m | Root cause hypothesis: config schema mismatch between v3.14 and v3.15 ops-agent |
| T+45m | Hypothesis confirmed; rollback initiated for 4 highest-risk customers |
| T+1h 10m | Hotfix identified; patch prepared |
| T+2h 05m | Patch validated in staging environment |
| T+3h 20m | Patch deployed to remaining affected customers; degradation resolved |
| T+4h 00m | Post-incident communication sent to all affected customers |

## Root Cause

The v3.15 release introduced a schema change to the ops-agent configuration file. The
self-hosted packaging process did not include a migration step for existing config files.
Customers upgrading from v3.14 with non-default configuration values encountered a silent
schema validation failure that caused the ops-agent to fall back to a default state,
breaking authentication token handling.

**Contributing factors:**
- The compatibility matrix for v3.15 did not cover the ops-agent schema change — it was added late in the release cycle and not surfaced in the release manifest
- Preflight checks did not include an ops-agent config validation step
- The release manifest for v3.15 was published without a rollback plan for the ops-agent path specifically
- No staging environment existed with a non-default ops-agent configuration

## Impact

| Impact area | Detail |
|---|---|
| Customer experience | 11 customers experienced degraded service for up to 3h 20m |
| Support load | 14 inbound tickets; 3 customer escalations to account management |
| Engineering time | ~40 engineer-hours across SRE, platform, and support |
| Revenue risk | Two customers requested SLA credits; one requested a post-incident call |
| Trust | Two customers asked for a written explanation of safeguards before resuming upgrades |

## Immediate Actions

| Action | Owner | Status |
|---|---|---|
| Publish hotfix as v3.15.1 with migration step included | Platform engineering | Done |
| Update compatibility matrix to include ops-agent schema changes | PM + release owner | Done |
| Send post-incident communication to all affected customers | Customer success + PM | Done |
| Add rollback reference for ops-agent path to release manifest template | PM | Done |

## Roadmap Consequences

This incident exposed two structural gaps that recurred in a different form three weeks
earlier (a cloud-side config validation failure in the control plane). The same class of
problem — schema change without migration path — caused both incidents.

This pattern meets the threshold for an explicit investment conversation:

| Roadmap item | Theme | Priority |
|---|---|---|
| Preflight check: ops-agent config schema validation | Upgrade safety | Now (add to current milestone) |
| Migration step requirement in release manifest template | Upgrade safety | Now |
| Non-default config staging environment for self-hosted | Upgrade safety | Next |
| Compatibility matrix coverage requirement for ops-agent changes | Release confidence | Now |

These items are now in the active backlog with owners. The pattern — schema change without
migration path — is added to the repeat-incident register. If a third instance occurs, it
escalates to an architecture conversation.

## What Changed In The Operating Model

The release manifest template now requires an explicit section for config schema changes
with a migration path or a documented rationale for why one is not needed. This is a
gate, not a recommendation — releases without it will not pass the readiness review.

## Read Next

[Platform Scorecard](07-platform-scorecard.md) — repeat-incident metric and upgrade
success rate both reflect this quarter's data.
