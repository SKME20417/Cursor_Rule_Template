# Cursor Rule Template

A production-ready set of [Cursor](https://cursor.sh) rules (`.mdc` files) and project documentation templates designed for building AI-powered SaaS platforms. Drop these into any repository to give Cursor's AI assistant deep architectural awareness and consistent engineering standards.

---

## What's Included

### Cursor Rules (`.cursor/rules/`)

| # | Rule File | Scope | Description |
|---|-----------|-------|-------------|
| 00 | `00-global-architect.mdc` | Always | Principal architect persona — clean architecture, separation of concerns, production-ready defaults, and doc-aware change behavior |
| 10 | `10-backend-fastapi.mdc` | `backend/**`, `api/**`, `*.py` | FastAPI + Pydantic + SQLAlchemy stack — thin routes, service layer, repository pattern, RESTful conventions, and structured project layout |
| 20 | `20-frontend-nextjs.mdc` | `frontend/**`, `components/**`, `app/**` | Next.js + TypeScript — small reusable components, accessible markup, centralized API clients, and clean state management |
| 30 | `30-database-postgres.mdc` | `models/**`, `migrations/**`, `db/**` | PostgreSQL persistence — migration-first schema changes, entity conventions (`id`, `created_at`, `updated_at`), tenant isolation, and repository-only DB access |
| 40 | `40-cache-redis.mdc` | `backend/**`, `workers/**`, `cache/**` | Redis caching and queues — intentional TTLs, stable key naming, idempotent workers, and separated cache vs queue semantics |
| 50 | `50-rag-system.mdc` | `ai/**`, `rag/**`, `embeddings/**` | RAG pipeline — separated ingestion/retrieval/generation stages, chunk metadata, source attribution, configurable retrieval parameters, and hallucination guards |
| 60 | `60-agents.mdc` | `agents/**`, `tools/**`, `workflows/**` | AI agent orchestration — modular planner/executor/tool architecture, input/output schemas for tools, memory separation, and policy-based multi-agent coordination |
| 70 | `70-security.mdc` | Always | Security baseline — no hardcoded secrets, input validation, auth enforcement, rate limiting, prompt injection resistance, and least-privilege access |
| 80 | `80-testing-quality.mdc` | Always | Testing and code quality — deterministic unit tests, integration tests for boundary-crossing flows, mocked externals, linting, and type safety |
| 90 | `90-devops-docker-aws.mdc` | `infra/**`, `docker/**`, `.github/**` | DevOps — optimized Dockerfiles, multi-stage builds, AWS managed services, least-privilege IAM, CI/CD gating, and rollback-safe deployments |
| 99 | `99-response-style.mdc` | Always | Response style — minimal precise changes, architecture-aware explanations, no toy code, and follow-up guidance for related files |

### Project Documentation (`docs/`)

| Document | Purpose |
|----------|---------|
| `PRD.md` | Product requirements — core users, modules (auth, tenancy, knowledge base, RAG chat, agents, billing, analytics), and success criteria |
| `ARCHITECTURE.md` | High-level architecture — component map, layering strategy, and guiding principles |
| `API_SPEC.md` | API specification — auth, organizations, knowledge base, chat/RAG, agents, and admin endpoints |
| `DB_SCHEMA.md` | Database schema — core tables (users, organizations, documents, embeddings, chat, agents, billing) and schema design rules |
| `DEPLOYMENT.md` | Deployment guide — local Docker Compose setup, AWS cloud deployment, and non-functional goals |

---

## Quick Start

### 1. Clone into your project

```bash
git clone https://github.com/euronone/Cursor-Rule-Template.git
```

### 2. Copy rules into your repo

```bash
cp -r Cursor-Rule-Template/.cursor/rules/ your-project/.cursor/rules/
cp -r Cursor-Rule-Template/docs/ your-project/docs/
```

### 3. Customize

- Edit the `globs` field in each `.mdc` file to match your project's directory structure.
- Update the docs under `docs/` to reflect your actual product, API, schema, and deployment setup.
- Add or remove rules as your stack evolves.

---

## Rule Design

Each rule follows a consistent structure:

```yaml
---
description: What this rule governs
globs: file-patterns/it/applies-to  # omitted for alwaysApply rules
alwaysApply: true                    # if it should apply globally
---
```

**Numbering convention:**
- `00–09` — Global / cross-cutting concerns
- `10–19` — Backend
- `20–29` — Frontend
- `30–39` — Database / persistence
- `40–49` — Caching / queues
- `50–59` — RAG / retrieval
- `60–69` — Agents / orchestration
- `70–79` — Security
- `80–89` — Testing / quality
- `90–98` — DevOps / infrastructure
- `99` — Response style

---

## Target Stack

These rules are tailored for the following stack but can be adapted to others:

- **Backend:** FastAPI, Pydantic, SQLAlchemy/SQLModel, Python
- **Frontend:** Next.js, TypeScript
- **Database:** PostgreSQL
- **Cache/Queue:** Redis
- **AI:** RAG pipelines, LLM-based agents, embedding/vector stores
- **Infra:** Docker, AWS, CI/CD

---

## License

This template is open source. Use it, fork it, adapt it to your needs.
