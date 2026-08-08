# Profile README Design

## Goal

Create a concise English GitHub profile README for Cho YunHo that positions him as a Cloud & Platform Engineer. The README should help hiring managers understand his focus quickly while giving engineers clear paths to inspect representative projects.

## Audience and Tone

- Primary audience: hiring managers and interviewers
- Secondary audience: engineers and potential collaborators
- Language: English only
- Tone: professional, concise, and technically credible
- Personality: limited to the clarity of the writing; no decorative visual effects are required

## Design Direction

Use a journey-first narrative. The three representative projects should show how one stage of platform engineering work led to the next:

1. K-Le-PaaS established the Kubernetes and GitOps foundation.
2. Heimdall applied those lessons to a focused Git-based preview deployment workflow.
3. Gjallar emerged during Heimdall development as Proxmox lifecycle and operational-risk concerns became a distinct product area.

This order is intentional. It prioritizes the engineering progression over reverse chronology.

## Information Architecture

The README will contain these sections in this order:

1. Name, role, and one-line introduction
2. What I Build
3. Platform Engineering Journey
4. Core Stack
5. Portfolio & Contact

The entire README should remain easy to scan and should not expand into a full resume. Detailed architecture, setup instructions, and project history belong in the linked project repositories and portfolio.

## Approved Content

### Profile Introduction

```md
# Cho YunHo | Cloud & Platform Engineer

I build cloud platforms and operational tools that make infrastructure delivery safer, repeatable, and easier to understand.

## What I Build

- Cloud platforms and internal developer tooling
- Git-driven deployment and operations workflows
- Safe, observable automation for Kubernetes and Proxmox environments
```

### Platform Engineering Journey

```md
## Platform Engineering Journey

### 01 — [K-Le-PaaS](https://github.com/K-Le-PaaS/backend-hybrid)
*Foundation · Team Project*

An AI-assisted Kubernetes platform that unified deployment, rollback, monitoring, and infrastructure operations.

Owned the project's infrastructure end-to-end, including Kubernetes and GitOps, while contributing to selected backend components for deployment automation.

`Kubernetes` · `GitOps` · `Argo CD` · `NCP` · `FastAPI` · `Prometheus`

### 02 — [Heimdall](https://github.com/CodingPenguin-yoon/Heimdall)
*Productization · Personal Project*

A Git-based preview deployment manager built to make deployment, release history, logs, and rollback easier to operate.

Applied the platform engineering lessons from K-Le-PaaS to build a focused and reproducible delivery workflow.

`Python` · `Docker` · `Git` · `FastAPI`

### 03 — [Gjallar](https://github.com/CodingPenguin-yoon/Gjallar)
*Specialization · Personal Project*

A human-facing Proxmox operations and risk console, separated from Heimdall as infrastructure lifecycle concerns grew.

Built around approval-gated operations, auditable execution, migration tracking, and reconciliation.

`Proxmox` · `FastAPI` · `React` · `PostgreSQL` · `Docker`
```

### Core Stack and Contact

```md
## Core Stack

- **Platform:** Kubernetes, Proxmox VE, Docker, GitOps, Argo CD
- **Cloud & Delivery:** Naver Cloud Platform, Helm, GitHub Actions
- **Backend:** Python, FastAPI, PostgreSQL, Redis
- **Frontend:** TypeScript, React, Next.js
- **Observability:** Prometheus, Grafana

## Portfolio & Contact

- **Portfolio:** [yoonman.page](https://yoonman.page)
- **Email:** [code.penguin.yoon@gmail.com](mailto:code.penguin.yoon@gmail.com)
```

## Visual Rules

- Use native GitHub Markdown with a clear heading hierarchy and whitespace.
- Do not add animated dots, particle effects, GIF banners, contribution snakes, or other motion.
- Do not add GitHub Stats cards or a large collection of badges.
- Present project technologies as short inline code labels.
- Present the broader core stack as categorized text lists.
- Do not add a hero image; the name, role, and introductory sentence should remain the visual entry point.

## Links

The implementation must use these public destinations:

- K-Le-PaaS: <https://github.com/K-Le-PaaS/backend-hybrid>
- Heimdall: <https://github.com/CodingPenguin-yoon/Heimdall>
- Gjallar: <https://github.com/CodingPenguin-yoon/Gjallar>
- Portfolio: <https://yoonman.page>
- Email: <mailto:code.penguin.yoon@gmail.com>

## Scope

Implementation is limited to replacing the default content in the repository-root `README.md`. No repository settings, GitHub profile fields, project READMEs, generated images, external assets, or automation workflows are part of this change.

## Acceptance Criteria

- The root README renders as an English-only GitHub profile README.
- The title identifies Cho YunHo as a Cloud & Platform Engineer.
- The README contains all five sections in the approved order.
- The journey appears as K-Le-PaaS, Heimdall, then Gjallar.
- K-Le-PaaS accurately distinguishes end-to-end infrastructure ownership from partial backend contribution.
- All project, portfolio, and email links use the destinations defined above.
- No animated assets, stats cards, badge walls, or unrelated sections are present.
- Markdown headings, lists, emphasis, inline code, and links render without syntax errors.
