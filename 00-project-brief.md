# Project Brief

## In One Line

Design and operate a platform system across Meridian's managed Kubernetes runtime, deployment artifacts, and SaaS management control plane so releases are safer, upgrade paths are clearer, and operational work is less manual.

## Scenario

Meridian runs on three tightly linked platform surfaces:

1. A managed Kubernetes platform on bare metal that powers the SaaS business
2. A self-hosted deployment layer spanning Helm charts, Docker Compose, and appliance images, serving regulated and air-gapped enterprise deployments alongside open-source community installs
3. An internal SaaS management control plane that handles tenant provisioning, upgrades, configuration, and lifecycle management

Each surface is individually important. The bigger problem is the seam between them. When those seams are poorly managed, the organization starts paying recurring tax in the form of:

- avoidable release friction
- upgrade confusion
- blind spots in observability and alerting
- repeated incidents
- manual operational work
- leadership surprise

## North Star

Make Meridian the easiest and safest cyber operations platform to deploy, upgrade, and operate in any supported environment.

## Why This Matters

Platform problems rarely announce themselves as platform problems. They appear as:

- missed dates
- support escalations
- risky upgrades
- engineering frustration
- executive requests for more status

When that happens, the wrong answer is usually more reporting. The right answer is a better operating system.

## Working Assumptions

These assumptions were made explicit at the start:

- Release truth is fragmented across GitHub, Notion, and Slack threads.
- Operational toil is materially consuming engineering capacity.
- Deployment artifact quality is strategically important for both enterprise customers and the open-source distribution; the same packaging pipeline serves both, with different support obligations.
- Observability and alert fidelity are inconsistent across critical services.
- Leadership wants predictability, but current signals are too late or too noisy.
- Incidents are generating local fixes, but not consistently reshaping priorities.

## Outcome Targets

| Outcome | Baseline | Target |
|---|---|---|
| Release-related escalations | 100 index | -30% |
| Supported upgrade success rate | 88% | 97% |
| Tenant provisioning lead time | 2 business days | same day for standard cases |
| Critical services with SLO and alert coverage | 6 of 9 | 9 of 9 |
| Repeat incidents | 100 index | -25% |
| Active epics with clear status and risk owner | 60% | 95% |

## Read Next

[Platform Thesis](01-platform-thesis.md)
