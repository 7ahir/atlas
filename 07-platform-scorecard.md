# Platform Scorecard

## Purpose

This scorecard is the operating view I would use with leadership and the platform team. It is designed to answer four questions:

1. Is delivery healthy?
2. Is the platform healthy?
3. Are releases and upgrades getting safer?
4. Are we reducing manual operational work?

## 1. Delivery Health

| Metric | Why it matters | Illustrative green / amber / red |
|---|---|---|
| Epics on track / at risk / off track | Shows whether the roadmap is still trustworthy | >80% on track / 60-80% / <60% |
| Blocked work older than 5 working days | Surfaces waiting cost | <3 / 3-6 / >6 |
| Scope churn inside active milestone | Reveals reactive planning | <10% / 10-20% / >20% |
| Interrupt load as % of capacity | Prevents roadmap fiction | <20% / 20-30% / >30% |

## 2. Platform Health

| Metric | Why it matters | Illustrative green / amber / red |
|---|---|---|
| SLO coverage on critical services | Shows whether expectations are explicit | >90% / 70-90% / <70% |
| MTTR | Measures recovery speed | Trending down / flat / trending up |
| Repeat incidents | Shows whether learning loops are working | Down quarter over quarter / flat / up |
| Change failure rate | Critical for release and upgrade confidence | <10% / 10-15% / >15% |

## 3. Upgrade And Release Health

| Metric | Why it matters | Illustrative green / amber / red |
|---|---|---|
| Supported upgrade success rate | Direct trust signal for deployment quality | >97% / 93-97% / <93% |
| Rollback rate | Measures rollout safety | <5% / 5-8% / >8% |
| Time from release candidate to artifact publication | Measures packaging efficiency | Trending down / flat / trending up |
| Releases with complete manifest and rollback plan | Measures readiness discipline | 100% / 80-99% / <80% |

## 4. Operational Leverage

| Metric | Why it matters | Illustrative green / amber / red |
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

## Read Next

[Executive Communication Samples](08-executive-communication-samples.md)
