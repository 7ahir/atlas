# Project Atlas: Platform PM Operating System

Prepared by [@7ahir](https://github.com/7ahir)

![Portfolio](https://img.shields.io/badge/Portfolio-Case%20Study-0F766E?style=flat-square)
![Role](https://img.shields.io/badge/Role-Platform%20PM-1D4ED8?style=flat-square)
![Scope](https://img.shields.io/badge/Scope-Cloud%20%2B%20Self--Hosted%20%2B%20Ops-7C3AED?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-Release%20Confidence-DC2626?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-Operational%20Leverage-CA8A04?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-Delivery%20Visibility-0EA5E9?style=flat-square)

![Project Atlas banner](assets/project-atlas-banner.svg)

> Delivery visibility, release confidence, and operational leverage for Meridian's three-surface cloud platform.

## What This Is

Project Atlas documents the platform PM operating system designed and installed for Meridian — a B2B infrastructure SaaS serving regulated enterprise customers across financial services and healthcare.

The platform spans:
- a managed cloud platform (AWS)
- a self-hosted deployment layer (.deb / .rpm) for air-gapped and regulated customers
- an internal SaaS operations control plane

The operating system connects these three surfaces into one release, delivery, and operational model.

## The Core Thesis

Platform PM is not backlog administration for infrastructure teams.

A strong Platform PM:
- makes release and upgrade reality visible
- reduces waiting caused by dependency and decision latency
- translates reliability, operability, and toil into business-legible tradeoffs
- installs a delivery system that helps engineers move with less friction
- turns incidents into roadmap consequences instead of recurring pain

Project Atlas shows how that was done at Meridian.

## System View

```mermaid
flowchart LR
    A["Managed cloud platform"] --> D["Platform PM operating system"]
    B["Self-hosted deployment layer"] --> D
    C["SaaS operations control plane"] --> D
    D --> E["Release confidence"]
    D --> F["Operational leverage"]
    D --> G["Delivery visibility"]
    D --> H["Leadership trust"]
```

## How To Read This

| Time | Path | What you will get |
|---|---|---|
| 2 min | [Hiring Manager Summary](HIRING_MANAGER_SUMMARY.md) | Fastest read on my point of view and why this portfolio matters |
| 5 min | [Project Brief](00-project-brief.md) -> [Platform Thesis](01-platform-thesis.md) -> [Roadmap](05-roadmap.md) | Fast read on the problem, point of view, and plan |
| 20 min | Add [Operating Model](03-operating-model.md) -> [Flagship Initiative](06-flagship-initiative.md) -> [Platform Scorecard](07-platform-scorecard.md) | How I run the work, not just how I describe it |
| Deep dive | Follow the files in order from `00` to `08` | Full diagnosis-to-execution arc |

## Artifact Map

| Phase | Artifact | What it demonstrates |
|---|---|---|
| 0. Framing | [Project Brief](00-project-brief.md) | Strategic framing and scope definition |
| 1. Point of view | [Platform Thesis](01-platform-thesis.md) | Clear understanding of what Platform PM owns and why it matters |
| 2. Diagnosis | [Current-State Assessment](02-current-state-assessment.md) | Ability to infer pain, risk, and operating seams before jumping to solutions |
| 3. Operating system | [Operating Model](03-operating-model.md) | Cadence design, decision hygiene, dependency management, and incident-to-roadmap loops |
| 4. Entry strategy | [30-60-90 Plan](04-30-60-90-plan.md) | How I would enter the role without thrashing the team |
| 5. Direction | [Roadmap](05-roadmap.md) | Outcome-led sequencing across platform surfaces |
| 6. Execution depth | [Flagship Initiative](06-flagship-initiative.md) | A concrete cross-surface initiative that proves platform PM leverage |
| 7. Measurement | [Platform Scorecard](07-platform-scorecard.md) | The metrics and review model used to govern delivery and platform health |
| 8. Communication | [Executive Communication Samples](08-executive-communication-samples.md) | How I keep leadership informed without falling into status theater |

## Scenario

Meridian is a B2B infrastructure SaaS (Series C, ~$85M ARR, 190 engineers) serving regulated enterprise customers. Its platform spans three coupled surfaces:

| Surface | Role in the business | Typical pain when unmanaged |
|---|---|---|
| Managed cloud platform | Runs the SaaS product | Reliability risk, unclear capacity, incident thrash |
| Self-hosted deployment layer | Serves security-sensitive and regulated customers | Upgrade failures, packaging drift, support burden |
| SaaS operations control plane | Handles provisioning, upgrades, and tenant lifecycle work | Manual toil, slow operations, uneven change safety |

The PM challenge is to make these three surfaces act like one product system.

## What Success Looks Like

By the end of two quarters, the platform organization should be visibly better at:

- shipping with fewer release and upgrade surprises
- making risk visible before dates slip
- reducing routine manual operations
- converting incident learning into product and platform changes
- giving leadership one coherent view of delivery and health

## About

Built by [@7ahir](https://github.com/7ahir) — platform PM case study for a multi-surface cloud infrastructure product.
