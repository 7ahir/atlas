# Platform Scorecard

## Purpose

This scorecard is the operating view used with Meridian's leadership and platform team. It is designed to answer four questions:

1. Is delivery healthy?
2. Is the platform healthy?
3. Are releases and upgrades getting safer?
4. Are we reducing manual operational work?

## 1. Delivery Health

| Metric | Why it matters | Green / Amber / Red |
|---|---|---|
| Epics on track / at risk / off track | Shows whether the roadmap is still trustworthy | >80% on track / 60-80% / <60% |
| Blocked work older than 5 working days | Surfaces waiting cost | <3 / 3-6 / >6 |
| Scope churn inside active milestone | Reveals reactive planning | <10% / 10-20% / >20% |
| Interrupt load as % of capacity | Prevents roadmap fiction | <20% / 20-30% / >30% |

## 2. Platform Health

| Metric | Why it matters | Green / Amber / Red |
|---|---|---|
| SLO coverage on SLA-linked services | Shows whether reliability obligations are explicit | >90% / 70-90% / <70% |
| Alert actionability on critical services | Shows whether observability improves decisions instead of creating noise | >80% / 60-80% / <60% |
| MTTR | Measures recovery speed | Trending down / flat / trending up |
| Repeat incidents | Shows whether learning loops are working | Down quarter over quarter / flat / up |
| Change failure rate | Critical for release and upgrade confidence | <10% / 10-15% / >15% |

## 3. Upgrade And Release Health

| Metric | Why it matters | Green / Amber / Red |
|---|---|---|
| Supported upgrade success rate | Direct trust signal for deployment quality | >97% / 93-97% / <93% |
| Rollback rate | Measures rollout safety | <5% / 5-8% / >8% |
| Time from release candidate to deployment artifact readiness | Measures packaging efficiency | Trending down / flat / trending up |
| Deployment guidance parity across supported paths | Prevents enterprise and community release paths from drifting apart | 100% / 80-99% / <80% |
| Releases with complete manifest and rollback plan | Measures readiness discipline | 100% / 80-99% / <80% |

## 4. Operational Leverage

| Metric | Why it matters | Green / Amber / Red |
|---|---|---|
| Tenant provisioning lead time | Exposes operational drag | same day / 1 business day / >1 day |
| Manual touchpoints per standard tenant action | Quantifies toil | trending down / flat / trending up |
| Time spent on recurring ops work | Shows whether automation is creating capacity | trending down / flat / trending up |
| Decision latency on cross-team blockers | Measures coordination quality | <2 days / 2-5 days / >5 days |

## Review Cadence

| View | Audience | Cadence |
|---|---|---|
| Delivery health | PM + platform leads | Weekly |
| Platform and release health | PM + leadership | Monthly |
| Operational leverage | PM + ops partners | Monthly |
| Full scorecard rollup | VP / Director / PM | Monthly |

## Scorecard Rules

- Never include a metric nobody trusts.
- Start with fewer metrics and stronger trust.
- Tie every red metric to an owner and next action.
- Track trends, not only snapshots.

## What This Prevents

- leadership surprise
- optimistic ETA fiction
- platform work that stays politically invisible
- endless debate about whether pain is real

## Q1 Sample Data

This is what the scorecard looked like at the end of Q1, six weeks after the operating model was installed.

### Delivery Health

| Metric | Q1 Result | Status | Commentary |
|---|---|---|---|
| Epics on track / at risk / off track | 3 on track / 2 at risk / 1 off track | Amber | Deployment artifact standardization slipped two weeks due to a signing-pipeline dependency that was not resolved in time |
| Blocked work older than 5 working days | 4 items | Amber | Two blockers with application engineering (API contract), one with security (artifact signing policy), one internal |
| Scope churn inside active milestone | 14% | Amber | Two scope additions to the unified release initiative after compatibility edge cases surfaced late |
| Interrupt load as % of capacity | 28% | Red | Interrupt load stayed above target for the full quarter and was flagged as a roadmap risk going into Q2 |

### Platform Health

| Metric | Q1 Result | Status | Commentary |
|---|---|---|---|
| SLO coverage on SLA-linked services | 6 of 9 services | Amber | Three services still without formal SLO and alert coverage; added to Q2 roadmap |
| Alert actionability on critical services | 68% actionable | Amber | Paging noise stayed high in two Kubernetes namespaces; alert review added to monthly health cadence |
| MTTR | Trending down (avg 47 min -> 31 min) | Green | Improvement driven by clearer incident owner assignment and runbook updates |
| Repeat incidents | 2 repeat classes identified | Amber | Both now have backlog items with owners; first fix targeted for Q2 |
| Change failure rate | 11% | Amber | Improved from 17% at start of quarter; target is below 10% |

### Upgrade And Release Health

| Metric | Q1 Result | Status | Commentary |
|---|---|---|---|
| Supported upgrade success rate | 91% | Amber | Up from 88% baseline; preflight checks were not yet live so some late-stage failures still occurred |
| Rollback rate | 6% | Amber | Two rollbacks this quarter; both documented with root cause and backlog items |
| Time from release candidate to deployment artifact readiness | Trending down (avg 9 days -> 6 days) | Green | Release manifest adoption reduced coordination lag across Helm, Docker Compose, and appliance paths |
| Deployment guidance parity across supported paths | 4 of 5 releases | Amber | Helm and appliance guidance shipped on time, but Docker Compose notes lagged the managed release by four days |
| Releases with complete manifest and rollback plan | 4 of 5 | Amber | One release missed a rollback plan due to a last-minute scope change; corrected in process for Q2 |

### Operational Leverage

| Metric | Q1 Result | Status | Commentary |
|---|---|---|---|
| Tenant provisioning lead time | 1 business day (standard cases) | Amber | Down from 2 days; target is same-day; automation v1 shipped mid-quarter |
| Manual touchpoints per standard tenant action | 4 (down from 7) | Green | Lifecycle automation v1 reduced manual steps materially |
| Time spent on recurring ops work | Trending down | Green | Estimated 12% capacity recovered from toil reduction in Q1 |
| Decision latency on cross-team blockers | 3.2 days average | Amber | Improved from no tracking baseline; target is under 2 days |

### Q1 Assessment

Two themes in amber reflect structural issues rather than execution failures:
- Interrupt load at 28% is the single biggest constraint on roadmap delivery. Q2 requires an explicit interrupt budget conversation with platform leadership before committing to new epics.
- SLO and alert coverage gaps mean platform health visibility is still incomplete. The monthly health review is running, but three services are still providing qualitative-only signals and noisy paging.

Green signals, especially MTTR improvement, deployment artifact readiness, and provisioning toil reduction, show the operating model is working where it has had time to take effect.

## Read Next

[Executive Communication Samples](08-executive-communication-samples.md)
