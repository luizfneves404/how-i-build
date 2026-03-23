# How I Build

Opinionated decision guides for technology choices. Each doc should have the below principles as guide. The principles will be the true reasons for making the choices in the specific guides, you only need to connect the choice to the principles. 

# Guides

- [Frontend](./Frontend.md) - also deals with streamlit (which blurs backend/frontend) and meta frameworks, which contain server-side code
- [Backend](./Backend.md) - strictly backend
- [Programming Language and dev Guide](./LanguageAndDev.md) - language and dev tooling
- [Language agnostic dev tooling](./Tooling.md) — editors, linters, formatters, package managers, CI/CD, containers, IaC
- [Data Layer](./DataLayer.md) — databases, ORMs, caching, file storage, search
- [Auth](./Auth.md) — authentication and identity management
- [AI](./AI.md)

# Software architecture and tech choice principles

These should guide the more specific guides.

## 1. Start with the SIMPLEST stack that solves the problem

**Prefer the architecture with the fewest moving parts you must understand and operate**
For frontend, for backend, for everything. Add more stuff later.
**Only exception**: if you foresee something VERY core to your idea that requires a more complex thing AND you need to start out with it because the switching cost is MUCH higher later.

## 2. Choose technologies based on reversibility and incrementability

**Hard to change → go for boring, conservative, big ecosystem.**

- Database engine
- Data model (SQL vs NoSQL)
- Programming Language
- Overall architecture (e.g. microservices vs monolith)
- Backend framework and (a bit less so) frontend framework

**Easy to change → experiment, find the absolute best one for your use case, even if isn't the best long-term**
- Dev tooling
- sometimes hosting/deployment (if you do it right, it's should be swappable, like CDNs and container deployment)

This aligns with open source.

Also:
MAKE YOUR DECISIONS SUCH THAT **your systems evolve by adding layers, not rewriting foundations.** As the project grows, everything should feel like it's stacking on top of what was before, not rewriting madly.

## 3. Prefer systems that verify correctness automatically

Language-level static guarantees. Database schema-level guarantees. Type-safety, especially end to end across the whole stack.
Tests that keep you grounded in reality and validate runtime.
Local dev setup and tests setup as similar as possible to prod.

## 4. Keep the codebase integrated

Monorepo mindset. favor full-stack commits/developers, tight integration and business rules instead of technical boundaries (like frontend vs backend). Decreases integration problems and speeds up iteration.
BUGS LOVE BOUNDARIES. THEY HIDE THERE AND FEAST. that ties into end to end type safety.

## 5. If you need infrastructure above simple, define it as code

You probably don't need more infrastructure (Rule 1). If you do, use the best IaC you can find. Don't hesitate to add.

## 6. Prefer flat-cost infrastructure once usage grows

A $10/month VPS handles significant traffic. BaaS platforms charge per read/write/compute-millisecond — cheap at zero users, painful at 100k.