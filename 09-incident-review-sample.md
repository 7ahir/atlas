# Incident Review: Self-Hosted Upgrade Failure — Meridian Platform v3.14 -> v3.15

## Summary

A self-hosted upgrade from v3.14 to v3.15 failed across 11 enterprise customers during a 3-hour window. Affected customers experienced degraded tenant provisioning and intermittent authentication failures. Four customers required rollback. No data loss occurred.

| Field | Detail |
|---|---|
| Date | Week 6 of Q1 |
| Duration | 3h 20m degraded, 45m to full recovery for rolling customers |
| Affected customers | 11 (7 degraded, 4 rolled back) |
| Surfaces affected | Deployment artifacts, SaaS management control plane |
| Severity | P1 (customer-impacting, multiple accounts) |
| Incident owner | Platform SRE lead |
| PM on incident | Platform PM |

## Timeline

| Time | Event |
|---|---|
| T+0 | First customer reports authentication errors post-upgrade via support |
| T+12m | Platform SRE begins investigation; two additional reports received |
| T+28m | Root cause hypothesis: values-schema mismatch between v3.14 and v3.15 tenant-manager components |
| T+45m | Hypothesis confirmed; rollback initiated for 4 highest-risk customers |
| T+1h 10m | Hotfix identified; patch prepared |
| T+2h 05m | Patch validated in staging environment |
| T+3h 20m | Patch deployed to remaining affected customers; degradation resolved |
| T+4h 00m | Post-incident communication sent to all affected customers |

## Root Cause

The v3.15 release introduced a schema change to the tenant-manager values file used by both the Helm chart and appliance bootstrap path. The self-hosted deployment bundle did not include a migration step for existing override files. Customers upgrading from v3.14 with non-default tenant-manager overrides encountered a silent reconciliation failure that caused the SaaS management control plane to fall back to a default state, breaking authentication token handling.

**Contributing factors:**
- The compatibility matrix for v3.15 did not cover the tenant-manager schema change across Helm and appliance paths because it was added late in the release cycle and not surfaced in the release manifest
- Preflight checks did not include values-schema validation against supported Kubernetes versions
- The release manifest for v3.15 was published without a rollback plan for the SaaS management path specifically
- No staging environment existed with non-default customer overrides on the oldest supported Kubernetes minor version

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
| Update compatibility matrix to include tenant-manager schema changes across Helm and appliance paths | PM + release owner | Done |
| Send post-incident communication to all affected customers | Customer success + PM | Done |
| Add rollback reference for the SaaS management path to the release manifest template | PM | Done |

## Roadmap Consequences

This incident exposed two structural gaps that recurred in a different form three weeks earlier: a cloud-side configuration validation failure in the managed Kubernetes promotion path and this self-hosted values-schema failure. The same class of problem, schema change without migration path, caused both incidents.

This pattern meets the threshold for an explicit investment conversation:

| Roadmap item | Theme | Priority |
|---|---|---|
| Preflight check: tenant-manager values-schema validation | Upgrade safety | Now (add to current milestone) |
| Migration step requirement in release manifest template | Upgrade safety | Now |
| Non-default override staging environment for self-hosted paths | Upgrade safety | Next |
| Compatibility matrix coverage requirement for SaaS management changes | Release confidence | Now |

These items are now in the active backlog with owners. The pattern, schema change without migration path, is added to the repeat-incident register. If a third instance occurs, it escalates to an architecture conversation.

## What Changed In The Operating Model

The release manifest template now requires an explicit section for configuration schema changes, supported Kubernetes versions, and a migration path or a documented rationale for why one is not needed. This is a gate, not a recommendation. Releases without it do not pass the readiness review.

## Read Next

[Platform Scorecard](07-platform-scorecard.md) — repeat-incident tracking and upgrade success both reflect this quarter's data.
