# Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the default GitHub profile README template with the approved English journey-first profile for Cho YunHo.

**Architecture:** Keep the implementation entirely in the repository-root `README.md` using native GitHub Markdown. The document will lead with role and engineering focus, tell the K-Le-PaaS → Heimdall → Gjallar progression, summarize the core stack, and end with direct portfolio and email links.

**Tech Stack:** GitHub Flavored Markdown, Git, `rg`, `curl`

## Global Constraints

- Modify only the repository-root `README.md` during implementation.
- Use English only in the rendered profile README.
- Keep the section order: introduction, What I Build, Platform Engineering Journey, Core Stack, Portfolio & Contact.
- Keep the project order: K-Le-PaaS, Heimdall, Gjallar.
- Describe K-Le-PaaS contribution as end-to-end infrastructure ownership, including Kubernetes and GitOps, plus selected backend contributions.
- Use `https://yoonman.page` for the portfolio and `mailto:code.penguin.yoon@gmail.com` for email.
- Do not add images, animations, GIFs, GitHub Stats cards, contribution snakes, or badge collections.
- Do not add dependencies, generated assets, workflows, or repository-setting changes.

## File Structure

- Modify: `README.md` — complete GitHub profile content and links
- Reference only: `docs/superpowers/specs/2026-08-08-profile-readme-design.md` — approved copy and acceptance criteria

---

### Task 1: Replace and Validate the Profile README

**Files:**
- Modify: `README.md`
- Test: `README.md` through content, whitespace, and public-link checks

**Interfaces:**
- Consumes: approved content and constraints from `docs/superpowers/specs/2026-08-08-profile-readme-design.md`
- Produces: a single GitHub-renderable profile document at `README.md`

- [ ] **Step 1: Confirm that the current default template does not satisfy the approved design**

Run:

```bash
rg -n '^# Cho YunHo \| Cloud & Platform Engineer$|^## What I Build$|^## Platform Engineering Journey$|^## Core Stack$|^## Portfolio & Contact$' README.md
```

Expected: no matches and exit status `1`, confirming that the approved profile sections are absent from the default template.

- [ ] **Step 2: Replace `README.md` with the approved content**

Write exactly:

```md
# Cho YunHo | Cloud & Platform Engineer

I build cloud platforms and operational tools that make infrastructure delivery safer, repeatable, and easier to understand.

## What I Build

- Cloud platforms and internal developer tooling
- Git-driven deployment and operations workflows
- Safe, observable automation for Kubernetes and Proxmox environments

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

- [ ] **Step 3: Verify required structure and ordering**

Run:

```bash
rg -n '^# Cho YunHo \| Cloud & Platform Engineer$|^## What I Build$|^## Platform Engineering Journey$|^### 01 — \[K-Le-PaaS\]|^### 02 — \[Heimdall\]|^### 03 — \[Gjallar\]|^## Core Stack$|^## Portfolio & Contact$' README.md
```

Expected: eight matches in ascending line-number order, with K-Le-PaaS before Heimdall and Heimdall before Gjallar.

- [ ] **Step 4: Verify content constraints and Markdown whitespace**

Run:

```bash
git diff --check
rg -n "Owned the project's infrastructure end-to-end, including Kubernetes and GitOps, while contributing to selected backend components for deployment automation\." README.md
rg -n 'https://yoonman\.page|mailto:code\.penguin\.yoon@gmail\.com' README.md
```

Expected: `git diff --check` exits `0`; the K-Le-PaaS contribution check returns one match; the contact check returns two matches.

Run:

```bash
rg -ni 'github-readme-stats|contribution.*snake|particle|animated|<img|!\[' README.md
```

Expected: no matches and exit status `1`.

- [ ] **Step 5: Verify public HTTP destinations**

Run:

```bash
curl -sS -I https://github.com/K-Le-PaaS/backend-hybrid
curl -sS -I https://github.com/CodingPenguin-yoon/Heimdall
curl -sS -I https://github.com/CodingPenguin-yoon/Gjallar
curl -sS -I https://yoonman.page
```

Expected: each command returns an HTTP `2xx` or `3xx` status. The email destination is validated syntactically in Step 4 because `mailto:` is not an HTTP endpoint.

- [ ] **Step 6: Review the final patch**

Run:

```bash
git diff -- README.md
git status --short
```

Expected: the diff replaces only the default `README.md` template; status lists only `README.md` as modified.

- [ ] **Step 7: Commit the implementation**

Run:

```bash
git add README.md
git commit -m "docs: add GitHub profile README"
```

Expected: one commit containing only the profile README implementation.
