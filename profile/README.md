Meekong · มีของ
===============

A Modern E-commerce Marketplace Platform
----------------------------------------

**Meekong (มีของ)** is a full-featured e-commerce marketplace platform built for scale — supporting
standard sales, real-time auctions, B2B quotations, and negotiation-based deals in a single unified system.
Engineered with a clean, service-oriented architecture and real-time infrastructure to handle
high-concurrency trading at marketplace scale.

* 🛒 Multi-modal marketplace — buy-now, auction, RFQ, and negotiation in one platform
* ⚡ Real-time bidding & notifications powered by Socket.IO + Redis Pub/Sub
* 🔎 Hybrid AI search with Meilisearch + OpenAI embeddings
* ☁️ Cloud-native on AWS (ap-southeast-7, Bangkok), containerized with Docker & ECS

### Trading Modes

* **Normal Sales** — Standard buy-now transactions
* **Auctions** — Time-based bidding with live real-time updates over WebSocket
* **RFQ** — B2B request-for-quotation and supplier responses
* **Satisfy** — Negotiation-based deals with offer / counter-offer flow

### Platform Architecture

Built as a **Turborepo monorepo** with **Bun** as the unified package manager. All Node.js services
follow **Clean Architecture** with Inversify dependency injection.

| Service | Stack | Role |
|---------|-------|------|
| **API** | Express + Prisma | Core business logic, source-of-truth schema |
| **Socket** | Fastify + Socket.IO + Drizzle | Real-time events, auctions, notifications |
| **Admin** | Next.js 15 + React 19 | Operations & management dashboard |
| **Web** | Next.js 16 + React 19 | Customer-facing storefront & landing |
| **AI** | Python + Meilisearch | Search indexing & hybrid retrieval |
| **Infra** | Terraform (AWS IaC) | Infrastructure as code |

* **Async processing** — BullMQ queues for media pipelines & auction lifecycle (winner, refund, forfeit, expiration)
* **Search sync** — PostgreSQL CDC (wal2json) → MeiliBridge → Meilisearch
* **Horizontal scaling** — Redis Pub/Sub fan-out across socket instances

### Technology Stack

<p align="left">
<a href="https://www.typescriptlang.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/typescript-colored.svg" alt="TypeScript" title="TypeScript" width="36" height="36" /></a>
<a href="https://nodejs.org/en/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/nodejs-colored.svg" alt="Node.js" title="Node.js" width="36" height="36" /></a>
<a href="https://nextjs.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/nextjs-colored-dark.svg" alt="Next.js" title="Next.js" width="36" height="36" /></a>
<a href="https://reactjs.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/react-colored.svg" alt="React" title="React" width="36" height="36" /></a>
<a href="https://expressjs.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/express-colored-dark.svg" alt="Express" title="Express" width="36" height="36" /></a>
<a href="https://tailwindcss.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/tailwindcss-colored.svg" alt="TailwindCSS" title="TailwindCSS" width="36" height="36" /></a>
<a href="https://ui.shadcn.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/shadcnui-colored.svg" alt="shadcn/ui" title="shadcn/ui" width="36" height="36" /></a>
<a href="https://www.postgresql.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/postgresql-colored.svg" alt="PostgreSQL" title="PostgreSQL" width="36" height="36" /></a>
<a href="https://redis.io/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/redis-colored.svg" alt="Redis" title="Redis" width="36" height="36" /></a>
<a href="https://www.python.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/python-colored.svg" alt="Python" title="Python" width="36" height="36" /></a>
<a href="https://www.docker.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/docker-colored.svg" alt="Docker" title="Docker" width="36" height="36" /></a>
<a href="https://aws.amazon.com" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/aws-colored-dark.svg" alt="AWS" title="AWS" width="36" height="36" /></a>
<a href="https://firebase.google.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/firebase-colored.svg" alt="Firebase" title="Firebase" width="36" height="36" /></a>
<a href="https://www.figma.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/figma-colored.svg" alt="Figma" title="Figma" width="36" height="36" /></a>
</p>

> Also powered by **Bun · Turborepo · Prisma · Drizzle · BullMQ · Meilisearch · Socket.IO · Omise · Terraform**

### Engineering Highlights

* 🧩 **Clean Architecture** across every service (api / business / data / shared layers) with DI containers
* 🔄 **CQRS-style data flow** — Prisma owns the schema, Drizzle reads it for low-latency socket queries
* 💳 **Payments** via Omise · **Push** via Firebase Cloud Messaging · **Auth** via JWT (access + refresh)
* 🚀 **CI/CD** — Jenkins pipelines deploying to ECS across DEV / UAT / PROD environments

---

<sub>🐲 Build by Meekong Team x <a href="https://github.com/uplift-technology-company-limited">Uplift Technology</a></sub>
