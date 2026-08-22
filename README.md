# Yunho Cho | Platform Engineer

I build deployment and operations platforms that standardize infrastructure changes, verify their outcomes, and preserve a clear recovery path.

## Focus

- Git-driven deployment workflows from a public repository's fixed `main` branch to a healthy Preview
- API-based Kubernetes and Proxmox operations with explicit execution boundaries
- Health checks, task tracking, failure handling, and operational history

## Selected Projects

### 01 — [Heimdall](https://github.com/CodingPenguin-yoon/heimdall_final)

_Git-based Preview deployment · Personal project · Alpha_

A self-hosted deployment manager that builds the `main` commit of a public GitHub repository as an isolated Docker candidate and promotes it to a stable Preview route only after health and route checks pass.

The normal deployment path keeps a failed candidate from replacing the active Preview. Ambiguous runtime states remain non-success and require reconciliation.

`Python` · `FastAPI` · `Docker` · `NGINX` · `PostgreSQL` · `React`

[Repository](https://github.com/CodingPenguin-yoon/heimdall_final) · [Case study](https://yoonman.page/projects/heimdall)

### 02 — [K-Le-PaaS](https://github.com/K-Le-PaaS/backend-hybrid)

_AI-assisted Kubernetes operations · Team project · Sep–Dec 2025_

The team built a cloud operations platform that connects web and Slack requests to Kubernetes operations, NCP deployment pipelines, monitoring, and notifications.

My contribution focused on Gemini-based command interpretation and Kubernetes status, log, external URL, restart, scaling, version rollback, and resource operations (PR #28); Prometheus-based NKS metric APIs and a WebSocket endpoint (PR #42); and per-user and repository service URL generation, storage, and lookup in the NCP SourceDeploy flow (PR #63).

`Kubernetes` · `Gemini` · `FastAPI` · `Prometheus` · `NCP`

[PR #28 — NLP / Kubernetes](https://github.com/K-Le-PaaS/backend-hybrid/pull/28) · [PR #42 — Monitoring](https://github.com/K-Le-PaaS/backend-hybrid/pull/42) · [PR #63 — Deployment URL](https://github.com/K-Le-PaaS/backend-hybrid/pull/63) · [Case study](https://yoonman.page/projects/klepaas)

### 03 — [Gjallar](https://github.com/CodingPenguin-yoon/Gjallar)

_Proxmox operations and risk console · Personal project · In progress_

A Proxmox operations and risk console that reads live inventory and records operation intent, action-specific acknowledgements or approvals, execution events, and post-checks. Product runtime reports `unconfigured`, `live`, or `degraded` connection state and does not fall back to demo inventory.

VM creation requires approval and final acknowledgement, while VM Start uses explicit acknowledgement and idempotency protection. Both operations track the Proxmox task and resulting state instead of treating an API response as final success.

`Proxmox VE` · `FastAPI` · `React` · `PostgreSQL` · `Docker`

[Repository](https://github.com/CodingPenguin-yoon/Gjallar) · [Case study](https://yoonman.page/projects/gjallar)

## Core Stack

- **Platform / Runtime:** Linux, Docker, Kubernetes, Proxmox VE, Naver Cloud Platform
- **Backend / Data:** Python, FastAPI, PostgreSQL, REST APIs, WebSocket
- **Delivery / Observability:** Git, NGINX, Prometheus, GitHub Actions
- **Network / Storage:** IPFire, WireGuard, reverse proxy, NFS, NAS

## Portfolio & Contact

- **Portfolio:** [yoonman.page](https://yoonman.page)
- **Resume:** [yoonman.page/resume](https://yoonman.page/resume)
- **Email:** [code.penguin.yoon@gmail.com](mailto:code.penguin.yoon@gmail.com)
