# Current-State Assessment

## Purpose

On joining Meridian, the initial assessment focused on testing these hypotheses before prescribing solutions. It is inference-based and deliberately structured to surface assumptions for early validation.

## The Three Product Surfaces

| Surface | Typical owner set | Likely pain when under-managed |
|---|---|---|
| Managed cloud platform | Platform engineering, SRE, leadership | Capacity blind spots, reliability debt, incident repeat patterns |
| Self-hosted deployment layer | Platform engineering, support, solution engineering | Packaging drift, version ambiguity, upgrade risk |
| SaaS operations control plane | Platform ops, engineering, customer-facing teams | Manual toil, inconsistent workflows, unsafe changes |

## Most Likely Signal Pattern

| Observable signal | Likely underlying issue |
|---|---|
| Leadership asks for frequent ad hoc status | Delivery truth is fragmented or low trust |
| Engineers complain about waiting on context or approvals | Dependency ownership is weak or unclear |
| Releases require heroics | Readiness model is informal or scattered |
| Support repeatedly handles upgrade confusion | Compatibility and upgrade guidance are not product-managed |
| Incident volume may be manageable, but repeat pain persists | Learning loops are weak even if response loops exist |
| Teams debate priorities late | Outcome framing and decision rights are blurry |

## Risk Clusters

| Risk cluster | What it means |
|---|---|
| Release drift | Cloud, self-hosted artifacts, and tenant tooling evolve on different rhythms, so every promotion becomes more coordination-heavy |
| Invisible toil | Repeated manual work in provisioning, upgrades, and compatibility work quietly consumes capacity |
| Interrupt tax | If incident and support work are not budgeted honestly, roadmap confidence becomes fiction |
| Decision latency | Some blockers are technical, but many are ownership, approval, or timing problems |
| Product-surface imbalance | One surface gets treated as the real product while the others become second-class |

## Dependency Seams Mapped First

| Seam | Why it matters |
|---|---|
| Platform engineering <-> application teams | Release coupling and environment expectations |
| Platform engineering <-> support / solution engineering | Upgrade quality and deployability feedback |
| Platform engineering <-> customer success | Provisioning and operational scale pain |
| PM <-> engineering leadership | Priority framing, ETA confidence, and escalation speed |
| PM <-> leadership | Risk visibility and tradeoff decisions |

## First Questions To Answer

1. Where does the organization currently store release truth?
2. Which recurring operational tasks consume the most unplanned time?
3. Which blockers age the longest, and why?
4. Which incidents repeat with only cosmetic fixes in between?
5. Which self-hosted upgrade paths create the most support burden?
6. Which metrics exist today, and which ones are currently guessed at?

## Initial Diagnosis

The initial diagnosis at Meridian was that the platform did not primarily have a "more process" problem. It had a legibility problem.

Different groups held different parts of the truth:
- engineers knew where the technical friction was
- support knew where customers got stuck
- leadership knew where predictability felt weak

The missing piece is a system that connects those truths into one operating model.

## Read Next

[Operating Model](03-operating-model.md)
