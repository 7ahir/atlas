# Current-State Assessment

## Purpose

On joining Meridian, the initial assessment focused on testing these hypotheses before prescribing solutions. It is inference-based and deliberately structured to surface assumptions for early validation.

## The Three Product Surfaces

| Surface | Typical owner set | Likely pain when under-managed |
|---|---|---|
| Managed Kubernetes platform | Platform engineering, SRE, infrastructure leadership | Capacity blind spots, observability drift, incident repeat patterns, SLA risk |
| Deployment artifacts | Platform engineering, support, solution engineering | Chart drift, version ambiguity, upgrade risk |
| SaaS management control plane | Platform ops, engineering, customer-facing teams | Manual toil, inconsistent workflows, unsafe changes |

## Most Likely Signal Pattern

| Observable signal | Likely underlying issue |
|---|---|
| Leadership asks for frequent ad hoc status | Delivery truth is fragmented or low trust |
| Engineers complain about waiting on context or approvals | Dependency ownership is weak or unclear |
| Releases require heroics | Readiness model and supported deployment paths are informal or scattered |
| Support repeatedly handles upgrade confusion from both enterprise teams and community operators | Compatibility and deployment guidance are not product-managed across all supported paths |
| Alerts fire often but still miss meaningful risk | Observability and alerting are not tuned to real operating needs |
| Incident volume may be manageable, but repeat pain persists | Learning loops are weak even if response loops exist |
| Teams debate priorities late | Outcome framing and decision rights are blurry |

## Risk Clusters

| Risk cluster | What it means |
|---|---|
| Release drift | Managed Kubernetes runtime, deployment artifacts, and SaaS management evolve on different rhythms, so every promotion becomes more coordination-heavy |
| Invisible toil | Repeated manual work in provisioning, upgrades, and compatibility validation quietly consumes capacity |
| Interrupt tax | If incident and support work are not budgeted honestly, roadmap confidence becomes fiction |
| Decision latency | Some blockers are technical, but many are ownership, approval, or timing problems |
| Product-surface imbalance | One surface gets treated as the real product while the others become second-class |
| Observability blind spots | Service health and SLA posture are guessed at rather than instrumented |
| Open-source and enterprise path divergence | Community and enterprise paths share release machinery but have different support obligations; if not managed explicitly, quality erodes on both sides |

## Dependency Seams Mapped First

| Seam | Why it matters |
|---|---|
| Platform engineering <-> application teams | Kubernetes release coupling and service expectations |
| Platform engineering <-> support / solution engineering | Deployment artifact quality and upgrade feedback |
| Platform engineering <-> customer success / security | Tenant lifecycle pain, audit needs, and escalation paths |
| PM <-> engineering leadership | Priority framing, ETA confidence, and escalation speed |
| PM <-> leadership | Risk visibility and tradeoff decisions |

## First Questions To Answer

1. Where does the organization currently store release truth?
2. Which recurring operational tasks consume the most unplanned time?
3. Which blockers age the longest, and why?
4. Which incidents repeat with only cosmetic fixes in between?
5. Which supported deployment paths create the most support burden, and how does it differ between enterprise and community operators?
6. Which critical services still lack trustworthy SLOs or actionable alerts?

## Initial Diagnosis

The initial diagnosis at Meridian was that the platform did not primarily have a "more process" problem. It had a legibility problem.

Different groups held different parts of the truth:
- engineers knew where the technical friction was
- support knew where customers got stuck
- leadership knew where predictability felt weak

The missing piece was a system that connected those truths into one operating model.

## Read Next

[Operating Model](03-operating-model.md)
