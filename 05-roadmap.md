# Roadmap

## Roadmap Philosophy

This is a Now / Next / Later roadmap anchored to outcomes, not features. Each initiative earns its place because it improves release confidence, operational leverage, or platform visibility in a way the business can understand.

## Assumed Capacity Model

Capacity is explicitly divided to keep the roadmap honest:

- 50% planned strategic work
- 30% reliability and operational health
- 20% interrupts and emergent work

If the real interrupt tax is higher, the roadmap must shrink before the team starts lying through optimism.

## Themes

| Theme | Why it matters |
|---|---|
| Release confidence | Fewer surprises across Kubernetes and self-hosted delivery |
| Operational leverage | Less manual work and safer routine tenant operations |
| Platform health visibility | Better decisions on observability, capacity, reliability, and SLA risk |
| Upgrade safety | Lower support burden and stronger customer trust |

## Now

| Initiative | Theme | Outcome | Gate |
|---|---|---|---|
| Unified release train and compatibility model | Release confidence | One release truth across platform surfaces | Readiness review trusted by all participating teams |
| Critical service observability, alerting, and capacity baseline | Platform health visibility | Service health becomes legible before incidents or SLA pain force action | Baseline dashboard adopted in monthly review |
| Tenant lifecycle automation v1 | Operational leverage | Standard provisioning and routine upgrade actions require fewer manual steps | Standard-case flow operational and measured |
| Deployment artifact standardization | Upgrade safety | Reduce variance across Helm, Docker Compose, and appliance releases | Supported path model and release checklist agreed |

## Next

| Initiative | Theme | Outcome | Gate |
|---|---|---|---|
| Self-hosted upgrade readiness checks | Upgrade safety | Catch environment-specific failures earlier | Preflight pass / fail logic used before release |
| Incident learning to backlog loop | Platform health visibility | Repeated pain translates into explicit investment decisions | Repeat-incident review in monthly health cadence |
| Progressive promotion for managed Kubernetes releases | Release confidence | Lower blast radius and better rollback posture | Promotion stages and rollback triggers defined |
| SaaS management workflow instrumentation | Operational leverage | Quantify where manual work still consumes capacity | Manual touchpoint baseline established |

## Later

| Initiative | Theme | Outcome | Gate |
|---|---|---|---|
| Environment profile catalog | Upgrade safety | Better deployment fit by customer environment | Supported archetypes documented and adopted |
| Compliance and audit evidence pack | Platform health visibility | Lower audit preparation drag and stronger enterprise trust | Evidence workflow integrated into operating model |
| Cross-surface release forecasting | Release confidence | Better ETA confidence and earlier tradeoff calls | Forecasting quality reaches useful signal level |

## Sequencing Logic

| Sequence | Why it comes now |
|---|---|
| Make truth visible first | Release and readiness truth must be explicit before the organization can coordinate reliably |
| Improve the platform's ability to see itself | SLOs, alerting, capacity baselines, and instrumentation are needed before leadership can make sensible tradeoffs |
| Remove repetitive manual work | Toil reduction creates capacity for everything else |
| Scale safety after visibility improves | Promotion logic, upgrade checks, and forecasting work better once the system is already legible |

## Roadmap Risks

- interrupt load may crowd out planned work
- application-team release behavior may need to change for shared release truth to work
- observability coverage may still be too thin for reliable SLA calls
- customer environment diversity can cause scope sprawl across deployment artifacts
- artifact standardization may feel bureaucratic if not tied to support and upgrade pain

## Read Next

[Flagship Initiative](06-flagship-initiative.md)
