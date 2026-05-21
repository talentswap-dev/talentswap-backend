<div align="center">

<!-- PROJECT LOGO / BANNER -->

```
 ╔═══════════════════════════════════════════════════════════╗
 ║                                                           ║
 ║  ████████╗ █████╗ ██╗    ███████╗███╗  ██╗████████╗     ║
 ║  ╚══██╔══╝██╔══██╗██║    ██╔════╝████╗ ██║╚══██╔══╝     ║
 ║     ██║   ███████║██║    █████╗  ██╔██╗██║   ██║        ║
 ║     ██║   ██╔══██║██║    ██╔══╝  ██║╚████║   ██║        ║
 ║     ██║   ██║  ██║██████╗███████╗██║ ╚███║   ██║        ║
 ║     ╚═╝   ╚═╝  ╚═╝╚═════╝╚══════╝╚═╝  ╚══╝  ╚═╝        ║
 ║                                                           ║
 ║           S W A P         B A C K E N D                  ║
 ║                                                           ║
 ╚═══════════════════════════════════════════════════════════╝
```

# TalentSwap — Backend API

### *A Peer-to-Peer Skill Barter Network powered by SkillPoints*

> **Status:** 🏗️ Pre-Development — Architecture & Planning Phase  
> This repository represents the complete backend architecture design, technical planning, and development roadmap for the TalentSwap platform. Implementation begins in Month 2.

---

[![NestJS](https://img.shields.io/badge/NestJS-10.x-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)](https://nestjs.com)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org)
[![Prisma](https://img.shields.io/badge/Prisma-ORM-2D3748?style=for-the-badge&logo=prisma&logoColor=white)](https://www.prisma.io)
[![Redis](https://img.shields.io/badge/Redis-7.x-DC382D?style=for-the-badge&logo=redis&logoColor=white)](https://redis.io)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com)
[![Railway](https://img.shields.io/badge/Railway-Deploy-0B0D0E?style=for-the-badge&logo=railway&logoColor=white)](https://railway.app)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Node.js Version](https://img.shields.io/badge/Node.js-20.x_LTS-339933?style=flat-square&logo=node.js)](https://nodejs.org)
[![Code Style](https://img.shields.io/badge/Code_Style-Prettier-F7B93E?style=flat-square&logo=prettier)](https://prettier.io)
[![GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-2088FF?style=flat-square&logo=github-actions)](https://github.com/features/actions)
[![Swagger](https://img.shields.io/badge/API_Docs-Swagger-85EA2D?style=flat-square&logo=swagger)](https://swagger.io)
[![Sentry](https://img.shields.io/badge/Monitoring-Sentry-362D59?style=flat-square&logo=sentry)](https://sentry.io)

</div>

---

## 📋 Table of Contents

<details>
<summary><strong>Click to expand full TOC</strong></summary>

- [Project Introduction](#-project-introduction)
- [Project Vision](#-project-vision)
- [Problem Statement](#-problem-statement)
- [Solution Overview](#-solution-overview)
- [Core Backend Responsibilities](#-core-backend-responsibilities)
- [System Architecture Overview](#-system-architecture-overview)
- [Backend Architecture Explanation](#️-backend-architecture-explanation)
- [Planned Backend Modules](#-planned-backend-modules)
- [Planned API Structure](#-planned-api-structure)
- [Planned Folder Structure](#-planned-folder-structure)
- [Planned Database Architecture](#️-planned-database-architecture)
- [Planned Prisma Schema Overview](#-planned-prisma-schema-overview)
- [Authentication Flow](#-authentication-flow)
- [Authorization & RBAC](#-authorization--rbac)
- [SkillPoints Wallet System](#-skillpoints-wallet-system)
- [Escrow & Transaction Workflow](#-escrow--transaction-workflow)
- [Redis Usage Strategy](#-redis-usage-strategy)
- [Real-Time Communication Architecture](#-real-time-communication-architecture)
- [Security Practices](#-security-practices)
- [Validation Strategy](#-validation-strategy)
- [Error Handling Strategy](#-error-handling-strategy)
- [Logging & Monitoring Strategy](#-logging--monitoring-strategy)
- [Scalability Considerations](#-scalability-considerations)
- [CI/CD Strategy](#-cicd-strategy)
- [Environment Configuration](#-environment-configuration)
- [Docker Setup Plan](#-docker-setup-plan)
- [API Documentation Strategy](#-api-documentation-strategy)
- [Git Workflow Strategy](#-git-workflow-strategy)
- [Coding Standards](#-coding-standards)
- [Development Roadmap](#-development-roadmap)
- [MVP Features](#-mvp-features)
- [Future Enhancements](#-future-enhancements)
- [Backend Milestones](#-backend-milestones)
- [Risks & Mitigations](#-risks--mitigations)
- [Learning Goals](#-learning-goals)
- [Backend Setup Instructions](#-backend-setup-instructions)
- [Environment Variables Reference](#-environment-variables-reference)
- [Available Scripts](#-available-scripts)
- [Example API Routes](#-example-api-routes)
- [API Response Format](#-api-response-format)
- [Queue & Job Processing Strategy](#-queue--job-processing-strategy)
- [WebSocket Gateway Planning](#-websocket-gateway-planning)
- [File Upload Architecture](#-file-upload-architecture)
- [Notification System Architecture](#-notification-system-architecture)
- [Rate Limiting & Security Protections](#️-rate-limiting--security-protections)
- [Testing Strategy](#-testing-strategy)
- [Performance Optimization Plan](#-performance-optimization-plan)
- [Recommended Dependencies](#-recommended-dependencies)
- [Contribution Guidelines](#-contribution-guidelines)
- [Team Structure](#-team-structure)
- [Acknowledgements](#-acknowledgements)
- [License](#-license)

</details>

---

## 🚀 Project Introduction

**TalentSwap** is a modern, full-stack peer-to-peer skill barter platform that enables users to exchange knowledge, services, and expertise without the need for money. At the core of TalentSwap is the **SkillPoints** economy — a virtual currency system that allows users to offer their skills, earn SkillPoints, and spend those points to access the skills of others in the community.

This repository contains the **backend API server** for the TalentSwap platform — a production-grade, scalable NestJS application built on TypeScript, PostgreSQL, and Redis. The backend handles all business logic, authentication, real-time communication, wallet transactions, AI-powered skill matching, file storage, background job processing, and administrative operations.

> ⚠️ **Architecture Notice:** This repository is currently in the **pre-development planning phase**. All architecture described in this README represents the **planned and proposed system design**. No production code has been deployed yet. Implementation begins in Month 2 of the development roadmap.

---

## 🌟 Project Vision

TalentSwap envisions a world where **expertise is the true currency**. We are building a community-first platform that democratises access to skills and knowledge by removing financial barriers. Whether you are a graphic designer who wants to learn Python, a musician who needs a website built, or a chef who wants to learn photography — TalentSwap makes skill exchange simple, safe, and rewarding.

The long-term vision for the platform:

- 🌍 Become the world's most trusted skill-barter community
- 🤝 Facilitate hundreds of thousands of skill exchanges monthly
- 🤖 Leverage AI to create perfect skill matches in under 30 seconds
- 🏅 Build a reputation and credential system that rivals professional portfolios
- 📱 Expand to mobile-native iOS and Android applications

---

## 🎯 Problem Statement

The modern gig economy is dominated by money-first platforms that create barriers for people who:

1. **Cannot afford to pay** for learning or professional services
2. **Lack confidence** to monetise their own skills on traditional freelancing platforms
3. **Want community** rather than transactional relationships
4. **Have valuable skills** but no professional credentials to prove them
5. **Need diverse learning** but face prohibitive subscription and course costs

Existing platforms like Fiverr, Upwork, and Skillshare are built around financial transactions, leaving an enormous underserved population of talented individuals who want to exchange value but not money.

---

## 💡 Solution Overview

TalentSwap solves these problems through a purpose-built barter economy:

| Problem | TalentSwap Solution |
|---|---|
| Financial barriers to accessing skills | SkillPoints virtual currency with no real money required |
| Lack of trust between strangers | Escrow system + verified reviews + credential badges |
| No way to prove informal skills | Community-validated skill endorsements and exchange history |
| Random, inefficient skill discovery | AI-powered matching engine using skill tags and availability |
| Fear of exploitation | Structured exchange agreements with milestone-based escrow |
| No motivation to give back | Gamification, leaderboards, and streak rewards |

---

## ⚙️ Core Backend Responsibilities

The backend API is the central nervous system of TalentSwap. It is responsible for:

```
┌─────────────────────────────────────────────────────────────┐
│               BACKEND CORE RESPONSIBILITIES                  │
├─────────────────────────────────────────────────────────────┤
│  🔐  Identity & Access        JWT auth, RBAC, refresh tokens │
│  👤  User Management          Profiles, preferences, KYC    │
│  🧠  Skill Intelligence        Listings, tags, AI matching   │
│  💰  SkillPoints Economy       Wallets, transfers, ledger    │
│  🔒  Escrow Engine            Holds, releases, disputes      │
│  💬  Real-Time Messaging      WebSocket gateway, chat rooms  │
│  🔔  Notifications            Push, email, in-app alerts     │
│  📋  Community Boards         Posts, replies, moderation     │
│  ⭐  Reputation System        Ratings, reviews, badges       │
│  📅  Scheduling               Availability, bookings         │
│  📁  File Management          Uploads, CDN delivery          │
│  📊  Analytics                Usage metrics, reporting       │
│  🛠️  Admin Operations         User management, oversight     │
│  🔄  Background Jobs          Queues, cron jobs, workers     │
│  🚀  Performance              Caching, rate limiting, CDN    │
└─────────────────────────────────────────────────────────────┘
```

---

## 🏗️ System Architecture Overview

The following diagram illustrates the full system architecture of the TalentSwap platform, from the client layer down to the data persistence layer:

```
┌────────────────────────────────────────────────────────────────────┐
│                        CLIENT LAYER                                │
│          Next.js 14 Web App  │  Mobile App (Future)               │
└──────────────────────────┬─────────────────────────────────────────┘
                           │  HTTPS / WSS
┌──────────────────────────▼─────────────────────────────────────────┐
│                     CLOUDFLARE EDGE                                │
│            CDN  │  DDoS Protection  │  WAF  │  DNS                │
└──────────────────────────┬─────────────────────────────────────────┘
                           │
              ┌────────────┴──────────────┐
              │                           │
┌─────────────▼─────────────┐  ┌─────────▼─────────────────────────┐
│      REST API Requests     │  │       WebSocket Connections        │
│   NestJS HTTP Controller   │  │      NestJS Socket.io Gateway      │
└─────────────┬─────────────┘  └─────────┬──────────────────────────┘
              │                           │
┌─────────────▼───────────────────────────▼──────────────────────────┐
│                     NESTJS APPLICATION CORE                         │
│                                                                     │
│   ┌─────────────┐  ┌──────────────┐  ┌──────────────────────────┐  │
│   │   Guards    │  │ Interceptors │  │  Exception Filters       │  │
│   │ JWT / RBAC  │  │ Logging/     │  │  Global Error Handler    │  │
│   │ Throttle    │  │ Transform    │  │  Zod Validation          │  │
│   └─────────────┘  └──────────────┘  └──────────────────────────┘  │
│                                                                     │
│   ┌─────────────────────────────────────────────────────────────┐  │
│   │                    FEATURE MODULES                          │  │
│   │  Auth │ Users │ Skills │ Wallet │ Escrow │ Messaging │ ...  │  │
│   └─────────────────────────────────────────────────────────────┘  │
│                                                                     │
│   ┌─────────────────────────────────────────────────────────────┐  │
│   │                   SERVICE LAYER                             │  │
│   │     Business Logic │ Domain Rules │ Data Transformation     │  │
│   └─────────────────────────────────────────────────────────────┘  │
└──────────┬───────────────────────┬──────────────────────┬──────────┘
           │                       │                      │
┌──────────▼──────────┐  ┌────────▼──────────┐  ┌────────▼──────────┐
│  Supabase           │  │  Redis 7           │  │  Cloudflare R2    │
│  PostgreSQL 16      │  │  Cache + BullMQ    │  │  Object Storage   │
│  Prisma ORM         │  │  Job Queues        │  │  File CDN         │
└─────────────────────┘  └───────────────────┘  └───────────────────┘
           │
┌──────────▼──────────┐
│  External Services  │
│  Sentry │ Resend    │
│  OpenAI │ Stripe*   │
└─────────────────────┘
```

> *Stripe integration is a future enhancement for premium features. SkillPoints are not real currency.

---

## 🛠️ Backend Architecture Explanation

The TalentSwap backend follows a **Modular Monolith** pattern using **Clean Architecture** principles. This means the codebase is organised as a single deployable application, but internally structured into fully decoupled, independently testable domain modules.

### Why Modular Monolith?

| Aspect | Decision | Reasoning |
|---|---|---|
| Deployment complexity | Single deployable unit | Appropriate for early stage; no DevOps overhead of microservices |
| Module separation | Feature-based modules | Each domain boundary is explicit and independently testable |
| Database | Single PostgreSQL instance | Shared DB simplifies transactions; can be split later if needed |
| Scalability path | Monolith → Microservices | Modules can be extracted into separate services as scale demands |
| Team size | 4 developers | Microservices at this team size adds coordination overhead |

### Architecture Layers

```
┌─────────────────────────────────┐
│         Controllers              │  ← HTTP / WebSocket handlers
├─────────────────────────────────┤
│           Services               │  ← Business logic & domain rules
├─────────────────────────────────┤
│        Repositories              │  ← Prisma data access layer
├─────────────────────────────────┤
│      Domain Models / DTOs        │  ← Data shapes & validation
├─────────────────────────────────┤
│      Infrastructure Layer        │  ← Redis, R2, Email, Queues
└─────────────────────────────────┘
```

### Request Lifecycle

```
Incoming HTTP Request
        │
        ▼
[Rate Limiter / Throttle Guard]
        │
        ▼
[JWT Authentication Guard]
        │
        ▼
[RBAC Role Guard]
        │
        ▼
[Zod / class-validator Pipe]
        │
        ▼
[Controller → Service → Repository]
        │
        ▼
[Response Interceptor → Standardised JSON]
        │
        ▼
Outgoing HTTP Response
```

---

## 📦 Planned Backend Modules

The backend is organised into the following **planned NestJS feature modules**:

| Module | Responsibility | Key Dependencies |
|---|---|---|
| `AuthModule` | Registration, login, JWT, refresh tokens, OAuth | Passport, bcrypt, JWT |
| `UsersModule` | User CRUD, profile management, settings | Prisma |
| `SkillsModule` | Skill listings, tags, categories, search | Prisma, Meilisearch (future) |
| `MatchingModule` | AI-powered skill matching engine | OpenAI API, Redis |
| `WalletModule` | SkillPoints balance, transactions, ledger | Prisma (ACID transactions) |
| `EscrowModule` | Exchange agreements, holds, releases, disputes | Prisma, BullMQ |
| `MessagingModule` | In-app DMs, chat threads, read receipts | Socket.io, Redis Pub/Sub |
| `NotificationsModule` | In-app, email, and push notifications | BullMQ, Resend |
| `ReviewsModule` | Ratings, written reviews, endorsements | Prisma |
| `SchedulingModule` | User availability, booking slots, calendars | Prisma |
| `CommunityModule` | Community boards, posts, replies, moderation | Prisma |
| `GamificationModule` | Badges, streaks, leaderboards, XP system | Prisma, Redis |
| `CredentialsModule` | Skill credential verification and endorsements | Prisma |
| `FilesModule` | Upload handling, Cloudflare R2 integration | Multer, AWS SDK |
| `AdminModule` | Admin dashboard APIs, user moderation, reports | Prisma, RBAC |
| `AnalyticsModule` | Platform metrics, usage reports, export | Prisma |
| `HealthModule` | Server health check and readiness endpoint | @nestjs/terminus |
| `PrismaModule` | Global Prisma service and connection pool | Prisma |
| `RedisModule` | Global Redis client, caching helpers | ioredis |
| `QueueModule` | BullMQ job definitions, workers, processors | BullMQ |
| `CommonModule` | Shared utilities, decorators, filters, guards | All modules |

---

## 🔗 Planned API Structure

All API routes follow the versioned prefix `/api/v1/`. The planned endpoint groups are:

```
/api/v1/
│
├── /auth
│   ├── POST   /register            Register a new user account
│   ├── POST   /login               Authenticate and receive tokens
│   ├── POST   /refresh             Refresh access token using refresh token
│   ├── POST   /logout              Revoke refresh token
│   ├── POST   /forgot-password     Initiate password reset flow
│   ├── POST   /reset-password      Complete password reset
│   └── POST   /verify-email        Verify email address
│
├── /users
│   ├── GET    /me                  Get authenticated user's profile
│   ├── PATCH  /me                  Update authenticated user's profile
│   ├── GET    /:id                 Get public user profile
│   ├── GET    /                    List users (admin only)
│   └── DELETE /:id                 Soft-delete user (admin only)
│
├── /skills
│   ├── GET    /                    List/search all skill listings
│   ├── POST   /                    Create new skill listing
│   ├── GET    /:id                 Get single skill listing
│   ├── PATCH  /:id                 Update skill listing
│   ├── DELETE /:id                 Delete skill listing
│   └── GET    /categories          List all skill categories
│
├── /matching
│   └── POST   /find                AI-powered skill match request
│
├── /wallet
│   ├── GET    /balance             Get current SkillPoints balance
│   ├── GET    /transactions        List transaction history
│   └── POST   /transfer            Transfer points to another user
│
├── /escrow
│   ├── POST   /initiate            Initiate a skill exchange agreement
│   ├── GET    /:id                 Get escrow details
│   ├── POST   /:id/confirm         Both parties confirm exchange
│   ├── POST   /:id/release         Release points after completion
│   └── POST   /:id/dispute         Open a dispute
│
├── /messages
│   ├── GET    /threads             List all conversation threads
│   ├── GET    /threads/:id         Get messages in a thread
│   └── POST   /threads             Start a new conversation thread
│
├── /reviews
│   ├── GET    /user/:userId        Get all reviews for a user
│   └── POST   /                    Submit a review after exchange
│
├── /notifications
│   ├── GET    /                    List all notifications
│   └── PATCH  /:id/read            Mark notification as read
│
├── /community
│   ├── GET    /posts               List community board posts
│   ├── POST   /posts               Create a new post
│   ├── GET    /posts/:id           Get single post with replies
│   └── POST   /posts/:id/replies   Reply to a post
│
├── /scheduling
│   ├── GET    /availability/:userId  Get user's available slots
│   └── POST   /availability          Set availability windows
│
├── /gamification
│   ├── GET    /leaderboard          Top earners / most exchanges
│   └── GET    /badges               Get authenticated user's badges
│
├── /files
│   └── POST   /upload               Upload a file to Cloudflare R2
│
├── /admin
│   ├── GET    /users                List all users with full detail
│   ├── PATCH  /users/:id/suspend    Suspend a user account
│   ├── GET    /disputes             List open disputes
│   └── POST   /disputes/:id/resolve Resolve a dispute
│
└── /health
    └── GET    /                     Server health and readiness check
```

---

## 📁 Planned Folder Structure

The following represents the **proposed directory layout** for the backend repository:

```
talentswap-backend/
│
├── src/
│   ├── main.ts                          # Application bootstrap
│   ├── app.module.ts                    # Root application module
│   │
│   ├── common/                          # Shared utilities across all modules
│   │   ├── decorators/
│   │   │   ├── current-user.decorator.ts
│   │   │   ├── public.decorator.ts
│   │   │   └── roles.decorator.ts
│   │   ├── filters/
│   │   │   ├── http-exception.filter.ts
│   │   │   └── prisma-exception.filter.ts
│   │   ├── guards/
│   │   │   ├── jwt-auth.guard.ts
│   │   │   └── roles.guard.ts
│   │   ├── interceptors/
│   │   │   ├── response-transform.interceptor.ts
│   │   │   └── logging.interceptor.ts
│   │   ├── pipes/
│   │   │   └── zod-validation.pipe.ts
│   │   ├── types/
│   │   │   ├── api-response.type.ts
│   │   │   └── jwt-payload.type.ts
│   │   └── utils/
│   │       ├── hash.util.ts
│   │       ├── pagination.util.ts
│   │       └── date.util.ts
│   │
│   ├── config/                          # Configuration using @nestjs/config
│   │   ├── app.config.ts
│   │   ├── database.config.ts
│   │   ├── jwt.config.ts
│   │   ├── redis.config.ts
│   │   └── storage.config.ts
│   │
│   ├── modules/                         # Feature modules
│   │   ├── auth/
│   │   │   ├── auth.module.ts
│   │   │   ├── auth.controller.ts
│   │   │   ├── auth.service.ts
│   │   │   ├── strategies/
│   │   │   │   ├── jwt.strategy.ts
│   │   │   │   └── jwt-refresh.strategy.ts
│   │   │   ├── dto/
│   │   │   │   ├── register.dto.ts
│   │   │   │   ├── login.dto.ts
│   │   │   │   └── refresh-token.dto.ts
│   │   │   └── __tests__/
│   │   │       └── auth.service.spec.ts
│   │   │
│   │   ├── users/
│   │   │   ├── users.module.ts
│   │   │   ├── users.controller.ts
│   │   │   ├── users.service.ts
│   │   │   ├── users.repository.ts
│   │   │   ├── dto/
│   │   │   │   ├── update-profile.dto.ts
│   │   │   │   └── user-response.dto.ts
│   │   │   └── __tests__/
│   │   │       └── users.service.spec.ts
│   │   │
│   │   ├── skills/
│   │   │   ├── skills.module.ts
│   │   │   ├── skills.controller.ts
│   │   │   ├── skills.service.ts
│   │   │   ├── skills.repository.ts
│   │   │   └── dto/
│   │   │       ├── create-skill.dto.ts
│   │   │       └── skill-response.dto.ts
│   │   │
│   │   ├── matching/
│   │   │   ├── matching.module.ts
│   │   │   ├── matching.controller.ts
│   │   │   └── matching.service.ts
│   │   │
│   │   ├── wallet/
│   │   │   ├── wallet.module.ts
│   │   │   ├── wallet.controller.ts
│   │   │   ├── wallet.service.ts
│   │   │   └── wallet.repository.ts
│   │   │
│   │   ├── escrow/
│   │   │   ├── escrow.module.ts
│   │   │   ├── escrow.controller.ts
│   │   │   ├── escrow.service.ts
│   │   │   └── escrow.repository.ts
│   │   │
│   │   ├── messaging/
│   │   │   ├── messaging.module.ts
│   │   │   ├── messaging.controller.ts
│   │   │   ├── messaging.service.ts
│   │   │   └── messaging.gateway.ts       # Socket.io WebSocket gateway
│   │   │
│   │   ├── notifications/
│   │   │   ├── notifications.module.ts
│   │   │   ├── notifications.controller.ts
│   │   │   ├── notifications.service.ts
│   │   │   └── processors/
│   │   │       └── notification.processor.ts
│   │   │
│   │   ├── reviews/
│   │   ├── scheduling/
│   │   ├── community/
│   │   ├── gamification/
│   │   ├── credentials/
│   │   ├── files/
│   │   ├── admin/
│   │   ├── analytics/
│   │   └── health/
│   │
│   ├── prisma/                          # Prisma integration
│   │   ├── prisma.module.ts
│   │   └── prisma.service.ts
│   │
│   └── redis/                           # Redis integration
│       ├── redis.module.ts
│       └── redis.service.ts
│
├── prisma/
│   ├── schema.prisma                    # Prisma schema definition
│   ├── migrations/                      # Auto-generated migration files
│   └── seed.ts                          # Database seed script
│
├── test/                                # End-to-end tests
│   ├── app.e2e-spec.ts
│   └── jest-e2e.json
│
├── docs/                                # Developer documentation
│   ├── adr/                             # Architecture Decision Records
│   │   └── 001-use-modular-monolith.md
│   ├── database.md                      # Database schema notes
│   └── setup.md                         # Local setup guide
│
├── .github/
│   └── workflows/
│       ├── ci.yml                       # Lint + build + test on PR
│       └── deploy.yml                   # Deploy to Railway on merge to main
│
├── docker-compose.yml                   # Local development stack
├── Dockerfile                           # Production container definition
├── .env.example                         # Environment variable template
├── .eslintrc.js                         # ESLint configuration
├── .prettierrc                          # Prettier configuration
├── nest-cli.json                        # NestJS CLI configuration
├── tsconfig.json                        # TypeScript base configuration
├── tsconfig.build.json                  # TypeScript build configuration
├── package.json
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 🗄️ Planned Database Architecture

The TalentSwap database is built on **PostgreSQL 16**, hosted via **Supabase**, and managed through **Prisma ORM**. The schema is designed around the following core entity groups:

### Entity Relationship Overview

```
┌──────────────────────────────────────────────────────────────────────┐
│                        CORE ENTITIES                                  │
│                                                                       │
│  ┌──────────┐    ┌─────────────┐    ┌──────────────┐                 │
│  │  users   │────│  profiles   │    │skill_listings│                 │
│  │          │    │             │    │              │                 │
│  │ id (PK)  │    │ user_id(FK) │    │ user_id (FK) │                 │
│  │ email    │    │ bio         │    │ title        │                 │
│  │ password │    │ avatar_url  │    │ description  │                 │
│  │ role     │    │ location    │    │ tags []      │                 │
│  │ status   │    │ skills []   │    │ points_rate  │                 │
│  └────┬─────┘    └─────────────┘    └──────────────┘                 │
│       │                                                               │
│  ┌────▼────────────────────────────────────────────────────────────┐  │
│  │                     ECONOMY ENTITIES                            │  │
│  │                                                                 │  │
│  │  ┌──────────────┐     ┌──────────────────┐                     │  │
│  │  │skill_wallets │     │skill_points_ledger│                    │  │
│  │  │              │     │                  │                     │  │
│  │  │ user_id (FK) │     │ wallet_id (FK)   │                     │  │
│  │  │ balance      │     │ type (CREDIT/     │                    │  │
│  │  │ reserved_bal │     │       DEBIT)      │                    │  │
│  │  │ total_earned │     │ amount           │                     │  │
│  │  └──────────────┘     │ reference_id     │                     │  │
│  │                       │ created_at       │                     │  │
│  │                       └──────────────────┘                     │  │
│  │                                                                 │  │
│  │  ┌──────────────────────────────────────────────┐              │  │
│  │  │                  escrow_pools                │              │  │
│  │  │                                              │              │  │
│  │  │ requester_id (FK)  │  provider_id (FK)       │              │  │
│  │  │ skill_listing_id   │  points_held            │              │  │
│  │  │ status (enum)      │  agreed_deliverables    │              │  │
│  │  │ expires_at         │  dispute_reason         │              │  │
│  │  └──────────────────────────────────────────────┘              │  │
│  └─────────────────────────────────────────────────────────────────┘  │
│                                                                       │
│  ┌────────────────────────────────────────────────────────────────┐   │
│  │                    SOCIAL ENTITIES                             │   │
│  │  messages │ threads │ reviews │ notifications │ community_posts│   │
│  │  badges │ user_badges │ availability_slots │ credentials       │   │
│  └────────────────────────────────────────────────────────────────┘   │
└──────────────────────────────────────────────────────────────────────┘
```

### Core Database Tables

| Table | Description | Key Fields |
|---|---|---|
| `users` | Primary user account data | `id`, `email`, `password_hash`, `role`, `status`, `email_verified_at` |
| `profiles` | Extended user information and preferences | `user_id`, `display_name`, `bio`, `avatar_url`, `location`, `availability_mode` |
| `skill_listings` | Skills users offer to teach or do | `user_id`, `title`, `description`, `category_id`, `points_rate`, `is_active` |
| `skill_categories` | Hierarchical skill taxonomy | `id`, `name`, `slug`, `parent_id` |
| `skill_tags` | Searchable tags on skill listings | `listing_id`, `tag` |
| `skill_wallets` | SkillPoints balance per user | `user_id`, `balance`, `reserved_balance`, `total_earned`, `total_spent` |
| `skill_points_ledger` | Immutable transaction log | `wallet_id`, `type`, `amount`, `reference_id`, `description`, `created_at` |
| `escrow_pools` | Holds for active exchanges | `requester_id`, `provider_id`, `listing_id`, `points_held`, `status`, `expires_at` |
| `messages` | Individual chat messages | `thread_id`, `sender_id`, `content`, `is_read`, `sent_at` |
| `message_threads` | Conversation containers | `participant_ids[]`, `last_message_at` |
| `reviews` | Ratings and written reviews | `reviewer_id`, `reviewee_id`, `escrow_id`, `rating`, `body` |
| `notifications` | In-app notification queue | `user_id`, `type`, `payload`, `is_read`, `created_at` |
| `community_posts` | Community board posts | `author_id`, `board_id`, `title`, `body`, `upvotes` |
| `availability_slots` | User availability windows | `user_id`, `day_of_week`, `start_time`, `end_time`, `is_recurring` |
| `badges` | Badge definitions | `id`, `name`, `description`, `icon_url`, `condition_type`, `threshold` |
| `user_badges` | Badges earned by users | `user_id`, `badge_id`, `earned_at` |
| `credentials` | Verifiable skill credentials | `user_id`, `title`, `issuer`, `issued_at`, `verification_url` |
| `refresh_tokens` | Active refresh token store | `user_id`, `token_hash`, `expires_at`, `is_revoked` |

---

## 📐 Planned Prisma Schema Overview

The following represents the **proposed Prisma schema structure**. This is a planning-phase overview; the actual schema will be refined during implementation.

```prisma
// prisma/schema.prisma

generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider  = "postgresql"
  url       = env("DATABASE_URL")
  directUrl = env("DIRECT_DATABASE_URL")
}

// ─── ENUMS ────────────────────────────────────────────────────────────────────

enum UserRole {
  USER
  MODERATOR
  ADMIN
}

enum UserStatus {
  ACTIVE
  SUSPENDED
  DEACTIVATED
  PENDING_VERIFICATION
}

enum EscrowStatus {
  INITIATED
  ACCEPTED
  IN_PROGRESS
  COMPLETED
  DISPUTED
  CANCELLED
  REFUNDED
}

enum LedgerEntryType {
  CREDIT
  DEBIT
  ESCROW_HOLD
  ESCROW_RELEASE
  ESCROW_REFUND
  BONUS
}

enum NotificationType {
  EXCHANGE_REQUEST
  EXCHANGE_ACCEPTED
  EXCHANGE_COMPLETED
  POINTS_RECEIVED
  NEW_MESSAGE
  NEW_REVIEW
  BADGE_EARNED
  SYSTEM
}

// ─── USER MANAGEMENT ─────────────────────────────────────────────────────────

model User {
  id                String     @id @default(cuid())
  email             String     @unique
  passwordHash      String     @map("password_hash")
  role              UserRole   @default(USER)
  status            UserStatus @default(PENDING_VERIFICATION)
  emailVerifiedAt   DateTime?  @map("email_verified_at")
  createdAt         DateTime   @default(now()) @map("created_at")
  updatedAt         DateTime   @updatedAt @map("updated_at")

  profile           Profile?
  wallet            SkillWallet?
  skillListings     SkillListing[]
  refreshTokens     RefreshToken[]
  sentMessages      Message[]      @relation("SentMessages")
  notifications     Notification[]
  badges            UserBadge[]
  givenReviews      Review[]       @relation("GivenReviews")
  receivedReviews   Review[]       @relation("ReceivedReviews")
  credentials       Credential[]
  availabilitySlots AvailabilitySlot[]
  communityPosts    CommunityPost[]
  requestedEscrows  EscrowPool[]   @relation("Requester")
  providedEscrows   EscrowPool[]   @relation("Provider")

  @@map("users")
}

model Profile {
  id              String   @id @default(cuid())
  userId          String   @unique @map("user_id")
  displayName     String   @map("display_name")
  bio             String?
  avatarUrl       String?  @map("avatar_url")
  location        String?
  availabilityMode String? @map("availability_mode")
  websiteUrl      String?  @map("website_url")
  totalExchanges  Int      @default(0) @map("total_exchanges")
  xpPoints        Int      @default(0) @map("xp_points")
  createdAt       DateTime @default(now()) @map("created_at")
  updatedAt       DateTime @updatedAt @map("updated_at")

  user            User     @relation(fields: [userId], references: [id], onDelete: Cascade)

  @@map("profiles")
}

// ─── SKILLS ───────────────────────────────────────────────────────────────────

model SkillCategory {
  id       String          @id @default(cuid())
  name     String          @unique
  slug     String          @unique
  parentId String?         @map("parent_id")
  parent   SkillCategory?  @relation("CategoryHierarchy", fields: [parentId], references: [id])
  children SkillCategory[] @relation("CategoryHierarchy")
  listings SkillListing[]

  @@map("skill_categories")
}

model SkillListing {
  id          String        @id @default(cuid())
  userId      String        @map("user_id")
  categoryId  String        @map("category_id")
  title       String
  description String
  pointsRate  Int           @map("points_rate")
  deliverables String?
  isActive    Boolean       @default(true) @map("is_active")
  createdAt   DateTime      @default(now()) @map("created_at")
  updatedAt   DateTime      @updatedAt @map("updated_at")

  user        User          @relation(fields: [userId], references: [id], onDelete: Cascade)
  category    SkillCategory @relation(fields: [categoryId], references: [id])
  tags        SkillTag[]
  escrows     EscrowPool[]

  @@map("skill_listings")
}

model SkillTag {
  id        String       @id @default(cuid())
  listingId String       @map("listing_id")
  tag       String
  listing   SkillListing @relation(fields: [listingId], references: [id], onDelete: Cascade)

  @@unique([listingId, tag])
  @@map("skill_tags")
}

// ─── ECONOMY ──────────────────────────────────────────────────────────────────

model SkillWallet {
  id               String       @id @default(cuid())
  userId           String       @unique @map("user_id")
  balance          Int          @default(100)   // Every new user gets 100 starter points
  reservedBalance  Int          @default(0) @map("reserved_balance")
  totalEarned      Int          @default(0) @map("total_earned")
  totalSpent       Int          @default(0) @map("total_spent")
  updatedAt        DateTime     @updatedAt @map("updated_at")

  user             User         @relation(fields: [userId], references: [id], onDelete: Cascade)
  ledgerEntries    LedgerEntry[]

  @@map("skill_wallets")
}

model LedgerEntry {
  id          String          @id @default(cuid())
  walletId    String          @map("wallet_id")
  type        LedgerEntryType
  amount      Int
  balanceAfter Int            @map("balance_after")
  referenceId String?         @map("reference_id")
  description String?
  createdAt   DateTime        @default(now()) @map("created_at")

  wallet      SkillWallet     @relation(fields: [walletId], references: [id])

  @@map("skill_points_ledger")
}

model EscrowPool {
  id               String       @id @default(cuid())
  requesterId      String       @map("requester_id")
  providerId       String       @map("provider_id")
  listingId        String       @map("listing_id")
  pointsHeld       Int          @map("points_held")
  status           EscrowStatus @default(INITIATED)
  agreedDeliverables String?    @map("agreed_deliverables")
  requesterConfirmed Boolean    @default(false) @map("requester_confirmed")
  providerConfirmed  Boolean    @default(false) @map("provider_confirmed")
  disputeReason    String?      @map("dispute_reason")
  expiresAt        DateTime     @map("expires_at")
  completedAt      DateTime?    @map("completed_at")
  createdAt        DateTime     @default(now()) @map("created_at")
  updatedAt        DateTime     @updatedAt @map("updated_at")

  requester        User         @relation("Requester", fields: [requesterId], references: [id])
  provider         User         @relation("Provider", fields: [providerId], references: [id])
  listing          SkillListing @relation(fields: [listingId], references: [id])
  reviews          Review[]

  @@map("escrow_pools")
}

// ─── SOCIAL ───────────────────────────────────────────────────────────────────

model Review {
  id         String     @id @default(cuid())
  reviewerId String     @map("reviewer_id")
  revieweeId String     @map("reviewee_id")
  escrowId   String     @map("escrow_id")
  rating     Int        // 1–5
  body       String?
  createdAt  DateTime   @default(now()) @map("created_at")

  reviewer   User       @relation("GivenReviews", fields: [reviewerId], references: [id])
  reviewee   User       @relation("ReceivedReviews", fields: [revieweeId], references: [id])
  escrow     EscrowPool @relation(fields: [escrowId], references: [id])

  @@unique([reviewerId, escrowId])
  @@map("reviews")
}

model Notification {
  id        String           @id @default(cuid())
  userId    String           @map("user_id")
  type      NotificationType
  title     String
  body      String?
  payload   Json?
  isRead    Boolean          @default(false) @map("is_read")
  createdAt DateTime         @default(now()) @map("created_at")

  user      User             @relation(fields: [userId], references: [id], onDelete: Cascade)

  @@map("notifications")
}

// (Additional models: Message, MessageThread, CommunityPost, Badge, UserBadge,
//  Credential, AvailabilitySlot, RefreshToken — to be defined during implementation)
```

---

## 🔐 Authentication Flow

TalentSwap uses a **JWT RS256 dual-token authentication system** with **automatic refresh token rotation**. This is the most secure approach for stateless APIs with persistent sessions.

```
REGISTRATION FLOW
─────────────────
1. User submits email + password
2. Backend validates with Zod schema
3. Password hashed with bcrypt (salt rounds: 12)
4. User record created with status = PENDING_VERIFICATION
5. Email verification token generated and sent via Resend
6. Starter SkillWallet created with 100 SkillPoints bonus
7. User profile record initialised
8. Response: 201 Created (no tokens yet — must verify email first)

LOGIN FLOW
──────────
1. User submits email + password
2. Backend looks up user by email
3. bcrypt.compare() validates password
4. User status and email verification checked
5. JWT Access Token generated (expiry: 15 minutes)
6. JWT Refresh Token generated (expiry: 30 days)
7. Refresh token hashed and stored in refresh_tokens table
8. Response: { accessToken, refreshToken, user }

TOKEN REFRESH FLOW
──────────────────
1. Client detects 401 Unauthorized response
2. Client sends refresh token to POST /auth/refresh
3. Backend validates refresh token signature and expiry
4. Backend checks token exists in DB and is not revoked
5. Old refresh token is deleted (single-use rotation)
6. New access token + new refresh token issued
7. Response: { accessToken, refreshToken }

LOGOUT FLOW
───────────
1. Client sends POST /auth/logout with refresh token
2. Backend deletes token record from DB
3. Access token naturally expires after 15 minutes
4. Response: 200 OK
```

### Token Architecture

| Property | Access Token | Refresh Token |
|---|---|---|
| Algorithm | RS256 (asymmetric) | RS256 (asymmetric) |
| Expiry | 15 minutes | 30 days |
| Storage (client) | Memory / httpOnly cookie | httpOnly Secure cookie |
| Server persistence | Stateless (JWT) | Hashed in database |
| Revocable | No (short-lived) | Yes (delete from DB) |
| Rotation | N/A | On every use |

---

## 🛡️ Authorization & RBAC

TalentSwap implements **Role-Based Access Control (RBAC)** with three distinct user roles:

| Role | Capabilities | Access Level |
|---|---|---|
| `USER` | Browse skills, create listings, exchange, message, review | Standard |
| `MODERATOR` | All USER actions + review community posts, manage disputes | Elevated |
| `ADMIN` | All MODERATOR actions + user management, platform config, analytics | Full |

### Guard Implementation (Planned)

```typescript
// Planned implementation

// 1. Apply @Public() decorator to bypass JWT on open routes
@Public()
@Post('register')
async register(@Body() dto: RegisterDto) { ... }

// 2. Apply @Roles() decorator for role-specific routes
@Roles(UserRole.ADMIN)
@Get('/admin/users')
async getAllUsers() { ... }

// 3. JWT guard applied globally in AppModule
// 4. Roles guard applied globally after JWT guard
```

### Guard Priority Chain

```
Request
   │
   ▼
ThrottlerGuard     ← Rate limiting check
   │
   ▼
JwtAuthGuard       ← Validates access token (skipped if @Public())
   │
   ▼
RolesGuard         ← Checks user.role against @Roles() decorator
   │
   ▼
Controller Handler
```

---

## 💰 SkillPoints Wallet System

The SkillPoints system is the economic backbone of TalentSwap. Every registered user receives a **SkillWallet** with **100 starter SkillPoints** upon registration.

### Wallet Rules

```
CORE INVARIANTS (must never be violated)
─────────────────────────────────────────
1. balance can NEVER go below 0
2. reserved_balance is always <= balance
3. spendable_balance = balance - reserved_balance
4. Every balance change MUST produce a LedgerEntry
5. All wallet operations run within Prisma transactions ($transaction)
6. No external mutations to the wallet — only WalletService may write
```

### SkillPoints Flow

```
New User Joins
     │
     ▼
SkillWallet created (balance: 100 starter points)
     │
     ├── User offers a skill → earns points from exchanges
     │         └── CREDIT entry added to ledger
     │
     └── User requests a skill → pays points into escrow
               └── ESCROW_HOLD entry added (balance reserved)
                         │
                         ├── Exchange completes → ESCROW_RELEASE to provider
                         └── Exchange cancelled → ESCROW_REFUND to requester
```

### Ledger Design

The `skill_points_ledger` table is an **append-only, immutable transaction log**. No entries are ever updated or deleted. This provides:
- Complete audit trail for every SkillPoints movement
- Ability to reconstruct wallet balance at any point in time
- Dispute resolution support with full transaction history
- Anti-fraud detection through pattern analysis

---

## 🔒 Escrow & Transaction Workflow

The escrow system ensures that both parties in a skill exchange are protected. Points are held in a virtual escrow pool until both parties confirm completion.

```
FULL ESCROW LIFECYCLE
──────────────────────

Step 1 — INITIATE
  Requester browses skill listing
  Requester clicks "Request Exchange"
  Backend checks: spendable_balance >= listing.points_rate
  Backend deducts from requester wallet (ESCROW_HOLD)
  EscrowPool record created with status = INITIATED
  Provider receives notification of incoming request

Step 2 — ACCEPT
  Provider reviews exchange terms
  Provider clicks "Accept"
  EscrowPool.status → ACCEPTED
  Both parties receive notifications
  Exchange chat thread created automatically

Step 3 — IN PROGRESS
  Provider begins delivering the skill
  Parties communicate via in-app messaging
  EscrowPool.status → IN_PROGRESS

Step 4 — CONFIRM COMPLETION
  Provider marks their side as done (providerConfirmed = true)
  Requester confirms receipt of skill (requesterConfirmed = true)
  When BOTH confirmed → auto-release triggered

Step 5 — RELEASE
  EscrowPool.status → COMPLETED
  Points transferred from escrow to provider wallet (ESCROW_RELEASE)
  Provider LedgerEntry: CREDIT
  Both users prompted to leave a review
  Both users earn XP points
  Achievement badges checked and awarded

DISPUTE FLOW
────────────
  Either party raises a dispute during IN_PROGRESS phase
  EscrowPool.status → DISPUTED
  Dispute reason recorded
  Moderator/Admin receives high-priority notification
  Admin reviews exchange history and messages
  Admin resolves: RELEASE to provider OR REFUND to requester
  EscrowPool.status → COMPLETED or REFUNDED

AUTO-EXPIRY
───────────
  If escrow not accepted within 72 hours → auto-cancelled via BullMQ job
  If in-progress for over 30 days with no activity → escalated to moderator
  Refund automatically issued on cancellation
```

---

## ⚡ Redis Usage Strategy

Redis 7 is used across the TalentSwap backend for four distinct purposes:

### 1. Response Caching

```
Cache Strategy: Cache-Aside (Lazy Loading)

┌─────────────┐    Cache HIT   ┌─────────────┐
│   Service   │───────────────▶│    Redis    │
│             │◀───────────────│   (data)   │
└─────────────┘                └─────────────┘

┌─────────────┐   Cache MISS   ┌─────────────┐    DB Query   ┌─────────┐
│   Service   │───────────────▶│    Redis    │──────────────▶│Postgres │
│             │                │  (no data)  │               │         │
│             │                └─────────────┘               └────┬────┘
│             │◀────────────────────────────────────────────────┘
│             │──── SET in Redis with TTL ────────────────────▶
└─────────────┘
```

### 2. Planned Cache Keys and TTLs

| Cache Key Pattern | Data Cached | TTL |
|---|---|---|
| `user:{id}:profile` | User profile data | 5 minutes |
| `skills:category:{slug}:page:{n}` | Paginated skill listings | 2 minutes |
| `leaderboard:weekly` | Top weekly exchangers | 10 minutes |
| `categories:all` | Skill category tree | 1 hour |
| `user:{id}:wallet:balance` | SkillPoints balance | 30 seconds |
| `matching:{userId}:suggestions` | AI match suggestions | 15 minutes |
| `community:posts:page:{n}` | Community board page | 1 minute |

### 3. Session & Token Storage

```
Planned usage:
- Store email verification tokens (TTL: 24 hours)
- Store password reset tokens (TTL: 1 hour)
- Store rate limit counters per IP/user
- Store Socket.io room membership data
```

### 4. BullMQ Job Queues

```
Queue: notifications     → Sends email and in-app notifications
Queue: escrow-expiry     → Checks and cancels expired escrow pools
Queue: ai-matching       → Processes async AI skill matching requests
Queue: badge-check       → Evaluates badge conditions after events
Queue: analytics         → Aggregates and writes analytics data
Queue: email             → Queues outbound transactional emails
```

### 5. Redis Pub/Sub for Real-Time

```
Channel: messages:{threadId}   → Broadcasts new messages to room members
Channel: notifications:{userId} → Pushes real-time notifications to user
Channel: presence:{userId}     → User online/offline status updates
```

---

## 📡 Real-Time Communication Architecture

TalentSwap uses **Socket.io** for all real-time features, integrated as a **NestJS WebSocket Gateway**.

```
WEBSOCKET CONNECTION LIFECYCLE
───────────────────────────────

Client connects → socket.handshake.auth.token verified (JWT)
                → User authenticated, userId extracted
                → Client joins personal room: join(`user:${userId}`)
                → Client joins thread rooms for active conversations

EVENTS (Server → Client)
─────────────────────────
message:new          New message received in a thread
notification:push    New real-time notification
escrow:updated       Escrow status changed (accept, complete, etc.)
user:online          Contact came online
user:typing          Contact is typing in shared thread
match:found          New AI skill match suggestion

EVENTS (Client → Server)
─────────────────────────
message:send         Send a message in a thread
message:read         Mark thread messages as read
typing:start         User started typing
typing:stop          User stopped typing
presence:ping        Heartbeat to maintain online status
```

### Planned Gateway Structure

```typescript
// Planned NestJS WebSocket Gateway (implementation phase)

@WebSocketGateway({
  cors: { origin: process.env.FRONTEND_URL },
  namespace: '/ws',
})
export class MessagingGateway
  implements OnGatewayInit, OnGatewayConnection, OnGatewayDisconnect
{
  @WebSocketServer() server: Server;

  afterInit(server: Server) { /* Redis adapter setup for horizontal scaling */ }
  handleConnection(client: Socket) { /* JWT validation, room joins */ }
  handleDisconnect(client: Socket) { /* Presence update, cleanup */ }

  @SubscribeMessage('message:send')
  handleMessage(@MessageBody() data: SendMessageDto) { ... }
}
```

---

## 🛡️ Security Practices

Security is built into every layer of the TalentSwap backend architecture.

### Planned Security Measures

| Layer | Measure | Implementation |
|---|---|---|
| **Transport** | HTTPS enforced everywhere | Cloudflare SSL/TLS |
| **Authentication** | RS256 JWT with short expiry | Passport.js + `@nestjs/jwt` |
| **Session** | Refresh token rotation with single-use enforcement | Database token store |
| **Password** | bcrypt hashing with cost factor 12 | `bcryptjs` package |
| **Input** | Strict schema validation on all inputs | Zod + class-validator |
| **Injection** | Parameterised queries only | Prisma ORM (no raw SQL by default) |
| **Rate Limiting** | IP-based throttling on all routes | `@nestjs/throttler` + Redis |
| **Auth endpoints** | Stricter rate limits on login/register | Per-route throttle overrides |
| **Headers** | Helmet.js security headers | `helmet` middleware |
| **CORS** | Strict whitelist of allowed origins | `@nestjs/common` CORS config |
| **Secrets** | Environment variables, never in code | `.env` + Railway secret management |
| **Dependencies** | Automated vulnerability scanning | GitHub Dependabot + npm audit |
| **Errors** | Production errors never expose stack traces | Custom exception filter |
| **Admin routes** | Double-guarded: JWT + Admin role | `JwtAuthGuard` + `RolesGuard` |
| **File uploads** | Type and size validation before processing | Multer filters |
| **Monitoring** | Real-time error alerting | Sentry |

---

## ✅ Validation Strategy

All incoming data is validated at the controller boundary before reaching any service or database layer.

### Dual Validation Approach

```
Request Body / Query / Params
           │
           ▼
┌──────────────────────────────┐
│    Zod Schema Validation     │  ← Primary: strict type-safe validation
│  (via custom Zod Pipe)       │
└────────────┬─────────────────┘
             │
             ▼
┌──────────────────────────────┐
│  class-validator decorators  │  ← Secondary: NestJS DTO-level validation
│  on DTO classes              │
└────────────┬─────────────────┘
             │
             ▼
      Controller Handler
```

### Validation Principles

- Every route has a corresponding Zod schema and DTO
- Validation errors return a consistent `400 Bad Request` with field-level error messages
- Unknown/extra fields are stripped by the validation pipe (whitelist mode)
- Enum values are validated at the schema level
- Numeric ranges (e.g., rating 1–5) enforced by validation
- String sanitisation applied to prevent XSS in stored content

---

## ❌ Error Handling Strategy

TalentSwap implements a **global exception filter** that intercepts all errors and transforms them into a consistent JSON response format.

### Error Response Format

```json
{
  "success": false,
  "statusCode": 404,
  "error": "NOT_FOUND",
  "message": "Skill listing with id 'clx...' was not found.",
  "timestamp": "2025-03-15T10:42:00.000Z",
  "path": "/api/v1/skills/clx..."
}
```

### Exception Types and Handling

| Exception Type | HTTP Status | When Used |
|---|---|---|
| `NotFoundException` | 404 | Entity not found by ID |
| `UnauthorizedException` | 401 | JWT missing, invalid, or expired |
| `ForbiddenException` | 403 | Valid JWT but insufficient role |
| `BadRequestException` | 400 | Validation failure |
| `ConflictException` | 409 | Duplicate email, unique constraint violation |
| `UnprocessableEntityException` | 422 | Business rule violation (e.g. insufficient points) |
| `InternalServerErrorException` | 500 | Unexpected server error (logged to Sentry) |
| `Prisma P2002` | 409 | Unique constraint (custom Prisma filter) |
| `Prisma P2025` | 404 | Record not found (custom Prisma filter) |

---

## 📊 Logging & Monitoring Strategy

### Application Logging

```typescript
// Planned logging approach using NestJS Logger + Sentry

// Request logging (Interceptor): every inbound request + response time
// Error logging (Filter): every unhandled exception with stack trace
// Business event logging (Service): key domain events (exchange started, etc.)
// Audit logging (Middleware): Admin actions logged with actor identity
```

### Log Levels by Environment

| Level | Development | Production |
|---|---|---|
| `DEBUG` | ✅ Enabled | ❌ Disabled |
| `LOG` | ✅ Enabled | ✅ Enabled |
| `WARN` | ✅ Enabled | ✅ Enabled |
| `ERROR` | ✅ Enabled | ✅ Enabled + Sentry alert |

### Sentry Integration Plan

- All unhandled exceptions sent to Sentry with full context
- Performance traces on API routes (target: < 200ms P95)
- Release tracking tied to GitHub deployment tags
- Sentry alerts via email on new issue types
- Custom Sentry breadcrumbs for business-critical flows (escrow, wallet)

---

## 📈 Scalability Considerations

The TalentSwap backend is architected to scale from hundreds to hundreds of thousands of users without architectural rewrites.

### Horizontal Scaling Strategy

```
Current (Phase 1)         Future (Phase 3+)
─────────────────         ─────────────────────────────
Single Railway instance   Multiple Railway instances (replicas)
Single PostgreSQL DB       Read replicas for query-heavy operations
Single Redis instance     Redis Cluster for high availability
BullMQ single worker      BullMQ multi-worker per queue
WebSocket single node     WebSocket with Redis Adapter (sticky sessions)
```

### Database Scaling Plan

| Strategy | When Applied | Benefit |
|---|---|---|
| Connection pooling (PgBouncer via Supabase) | Day 1 | Limits DB connections under load |
| Indexed queries on all FK and search fields | Day 1 | Fast lookups at any scale |
| Cursor-based pagination (not offset) | Day 1 | Consistent performance on large tables |
| Read replicas | Phase 3 | Offload analytics and reporting queries |
| Table partitioning on ledger entries | Phase 4 | Manage hundreds of millions of ledger rows |
| Archival of old notifications/messages | Phase 3 | Keep primary tables lean |

---

## 🔄 CI/CD Strategy

```
GITHUB ACTIONS PIPELINE
────────────────────────

On Pull Request (develop branch):
  1. Trigger: push to any feature/* or fix/* branch with PR to develop
  2. Job: Lint → eslint --ext .ts src/
  3. Job: Type Check → tsc --noEmit
  4. Job: Unit Tests → jest --coverage
  5. Job: Build Check → npm run build
  6. Status: All must pass before PR can be merged

On Merge to develop:
  1. Trigger: merge to develop branch
  2. Job: Full test suite
  3. Job: Build Docker image
  4. Job: Push image to registry
  5. Job: Deploy to Railway staging environment

On Merge to main (Production):
  1. Trigger: merge to main (release tag)
  2. Job: Full test suite + integration tests
  3. Job: Build production Docker image
  4. Job: Deploy to Railway production
  5. Job: Run database migrations (prisma migrate deploy)
  6. Job: Sentry release notification
  7. Job: Smoke test on health endpoint
```

---

## 🔧 Environment Configuration

All environment variables are managed via `@nestjs/config` with schema validation on startup. The application **will refuse to start** if required variables are missing or malformed.

### Environment Files

```
.env.example    ← Template committed to repository (no secrets)
.env            ← Local development (git-ignored)
.env.test       ← Test environment (git-ignored)
Railway Secrets ← Production secrets managed via Railway dashboard
```

---

## 🐳 Docker Setup Plan

### Planned `docker-compose.yml` for Local Development

```yaml
# docker-compose.yml (planned)

version: '3.9'

services:
  # ── NestJS Backend API ──────────────────────────────────────────────────────
  api:
    build:
      context: .
      dockerfile: Dockerfile.dev
    container_name: talentswap_api
    ports:
      - '3001:3001'
    environment:
      - NODE_ENV=development
      - DATABASE_URL=postgresql://postgres:password@postgres:5432/talentswap
      - REDIS_URL=redis://redis:6379
    volumes:
      - .:/app
      - /app/node_modules
    depends_on:
      - postgres
      - redis
    command: npm run start:dev
    restart: unless-stopped

  # ── PostgreSQL Database ──────────────────────────────────────────────────────
  postgres:
    image: postgres:16-alpine
    container_name: talentswap_postgres
    ports:
      - '5432:5432'
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
      POSTGRES_DB: talentswap
    volumes:
      - postgres_data:/var/lib/postgresql/data
    restart: unless-stopped

  # ── Redis Cache & Queue ───────────────────────────────────────────────────────
  redis:
    image: redis:7-alpine
    container_name: talentswap_redis
    ports:
      - '6379:6379'
    volumes:
      - redis_data:/data
    command: redis-server --appendonly yes
    restart: unless-stopped

  # ── Mailhog (Local Email Testing) ─────────────────────────────────────────────
  mailhog:
    image: mailhog/mailhog:latest
    container_name: talentswap_mailhog
    ports:
      - '1025:1025'   # SMTP
      - '8025:8025'   # Web UI → http://localhost:8025
    restart: unless-stopped

volumes:
  postgres_data:
  redis_data:
```

### Planned Production `Dockerfile`

```dockerfile
# Dockerfile (planned production build)

# ── Stage 1: Build ─────────────────────────────────────────────────────────────
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

# ── Stage 2: Production ────────────────────────────────────────────────────────
FROM node:20-alpine AS runner
WORKDIR /app
ENV NODE_ENV=production

COPY package*.json ./
RUN npm ci --only=production && npm cache clean --force

COPY --from=builder /app/dist ./dist
COPY --from=builder /app/prisma ./prisma

RUN addgroup --system appgroup && adduser --system appuser --ingroup appgroup
USER appuser

EXPOSE 3001
CMD ["node", "dist/main.js"]
```

---

## 📖 API Documentation Strategy

The TalentSwap backend will use **Swagger UI** (powered by `@nestjs/swagger`) for interactive API documentation.

```
Swagger Documentation available at:
  Development: http://localhost:3001/api/docs
  Staging:     https://staging.api.talentswap.dev/api/docs
  Production:  Not publicly exposed (admin access only)

Documentation Standards:
  - Every controller method has @ApiOperation() with summary + description
  - Every DTO has @ApiProperty() on all fields with example values
  - Every response type has @ApiResponse() with status codes documented
  - Authentication is documented via Swagger's BearerAuth mechanism
  - Request/response examples provided for all critical routes
```

---

## 🌿 Git Workflow Strategy

TalentSwap uses **GitHub Flow** with a protected `develop` integration branch.

### Branch Strategy

```
main
  └─ develop (integration)
         ├─ feature/TS-12-auth-module
         ├─ feature/TS-15-wallet-system
         ├─ fix/TS-22-escrow-race-condition
         ├─ docs/TS-6-api-documentation
         └─ chore/TS-8-update-dependencies
```

### Branch Naming Convention

```
feature/[ticket-id]-short-description
fix/[ticket-id]-short-description
docs/[ticket-id]-short-description
chore/[ticket-id]-short-description
refactor/[ticket-id]-short-description
test/[ticket-id]-short-description

Examples:
  feature/TS-25-websocket-messaging-gateway
  fix/TS-31-refresh-token-rotation-bug
  docs/TS-6-backend-readme
  chore/TS-44-upgrade-nestjs-v11
```

### Commit Message Convention

```
type(scope): short description [max 72 chars]

Types:
  feat     → New feature or capability
  fix      → Bug fix
  docs     → Documentation only
  chore    → Build scripts, config, dependencies
  refactor → Code restructure with no behaviour change
  test     → Adding or updating tests
  style    → Formatting, whitespace (no logic change)
  perf     → Performance improvement

Examples:
  feat(auth): implement JWT refresh token rotation
  fix(wallet): prevent double-debit on concurrent escrow creation
  docs(readme): add SkillPoints wallet system explanation
  chore(deps): upgrade Prisma to v5.10
  test(escrow): add unit tests for dispute resolution service
```

### Pull Request Rules

- Every PR requires at least **1 approved review** before merge
- PR title must follow commit message format
- PR description must include: what changed, why, and Linear ticket link
- All CI checks must pass (lint, type check, tests, build)
- **Squash merge only** — keeps `develop` history clean
- Delete branch immediately after merge

---

## 📋 Coding Standards

### TypeScript Configuration

```json
// tsconfig.json (planned)
{
  "compilerOptions": {
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "target": "ES2022",
    "module": "CommonJS",
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true
  }
}
```

### Code Style Rules

```
- 2-space indentation
- 100-character line length limit
- Single quotes for strings
- Trailing commas in multi-line structures
- Explicit return types on all public functions
- No `any` type (except justified exceptions with comment)
- Barrel exports (index.ts) for each module's public API
- PascalCase for classes, interfaces, enums
- camelCase for variables, functions, methods
- UPPER_SNAKE_CASE for constants
- kebab-case for file names (auth.service.ts, not AuthService.ts)
```

---

## 🗺️ Development Roadmap

### Month-by-Month Execution Plan

| Month | Theme | Key Deliverables |
|---|---|---|
| **Month 1** | Foundation & Setup | GitHub org, environments, CI/CD, README, scaffolding |
| **Month 2** | Core Backend | NestJS scaffold, auth module, users module, Prisma schema, migrations |
| **Month 3** | Economy Engine | Wallet system, escrow engine, ledger, SkillPoints transactions |
| **Month 4** | Social Layer | Messaging, notifications, reviews, community boards |
| **Month 5** | Intelligence & Polish | AI matching, gamification, scheduling, credential verification |
| **Month 6** | Production Hardening | Full test suite, performance optimisation, monitoring, launch |

---

## 🎯 MVP Features

The Minimum Viable Product (MVP) backend must support:

| Feature | Priority | Module |
|---|---|---|
| User registration and email verification | 🔴 Critical | Auth |
| JWT login and refresh token rotation | 🔴 Critical | Auth |
| User profile creation and editing | 🔴 Critical | Users |
| Skill listing creation and search | 🔴 Critical | Skills |
| SkillPoints wallet with ledger | 🔴 Critical | Wallet |
| Escrow-based exchange flow (initiate → complete) | 🔴 Critical | Escrow |
| In-app messaging between users | 🟠 High | Messaging |
| Post-exchange ratings and reviews | 🟠 High | Reviews |
| Email notifications for key events | 🟠 High | Notifications |
| Real-time notifications via WebSocket | 🟠 High | Messaging |
| Health endpoint for deployment monitoring | 🟠 High | Health |
| Swagger API documentation | 🟡 Medium | Config |
| Admin user management APIs | 🟡 Medium | Admin |
| File upload for avatars and attachments | 🟡 Medium | Files |

---

## 🚀 Future Enhancements

Features planned for post-MVP releases:

- 🤖 **AI-Powered Matching** — OpenAI-based semantic skill matching
- 📹 **Video/Voice Calls** — WebRTC integration for live skill sessions
- 📱 **Mobile Applications** — React Native iOS and Android apps
- 🏆 **Advanced Gamification** — Streak systems, XP levels, achievement trees
- 🌐 **Internationalisation** — Multi-language platform support
- 💳 **Premium Membership** — Paid tiers unlocking advanced features
- 🔗 **OAuth Providers** — Google, GitHub, LinkedIn login
- 📊 **Advanced Analytics** — Real-time dashboard with data visualisation
- 🤝 **Group Exchanges** — Multi-party skill exchange circles
- 🌍 **Localisation Engine** — Location-based skill matching
- 🔍 **Full-Text Search** — Meilisearch integration for powerful skill discovery
- 📋 **Portfolio Builder** — Exportable skill exchange history as a portfolio

---

## 🏁 Backend Milestones

| Milestone | Target Month | Definition of Done |
|---|---|---|
| M1: Repository Live | Month 1 | Repo exists, CI passes, health endpoint running |
| M2: Auth Complete | Month 2 | Registration, login, refresh, logout all tested |
| M3: Wallet Live | Month 3 | SkillPoints transfers work end-to-end with ledger |
| M4: First Exchange | Month 3 | Full escrow cycle completes in staging |
| M5: Messaging Live | Month 4 | Real-time chat works between two users |
| M6: AI Matching | Month 5 | Skill match suggestions return in < 3 seconds |
| M7: Full Test Coverage | Month 6 | Unit + integration tests at 80%+ coverage |
| M8: Production Launch | Month 6 | All MVP features live, monitoring active |

---

## ⚠️ Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation Strategy |
|---|---|---|---|
| Scope creep beyond MVP | High | High | Strict ticket discipline in Linear; Monthly scope reviews |
| Database race conditions in wallet/escrow | Medium | Critical | Prisma `$transaction` + database-level locks on sensitive operations |
| Free tier limits (Railway/Supabase) | Medium | Medium | Monitor usage weekly; prepare upgrade path |
| JWT token security misconfiguration | Low | Critical | Code review every auth change; automated security linting |
| Redis becomes unavailable | Low | High | Graceful degradation mode; critical paths do not depend solely on cache |
| Team member blocked on a task | High | Medium | Escalate within 24 hours; pair programming sessions |
| WebSocket scaling issues | Low | Medium | Redis Pub/Sub adapter planned from day one for horizontal scale |
| AI API costs spike | Medium | Medium | Cache AI responses aggressively; rate limit matching requests |

---

## 🎓 Learning Goals

This project is also a structured learning journey for the team. Backend development goals include:

| Skill Area | Technology | Goal |
|---|---|---|
| API Design | REST + NestJS | Build a complete, well-structured API from scratch |
| Type Safety | TypeScript (strict mode) | Write fully typed code with zero `any` |
| Database Design | PostgreSQL + Prisma | Design a relational schema with proper normalisation |
| Authentication | JWT + Passport.js | Implement production-grade auth with token rotation |
| Caching | Redis + ioredis | Apply real caching strategies to reduce DB load |
| Background Jobs | BullMQ | Process asynchronous tasks reliably with queues |
| Real-Time | Socket.io | Build bidirectional real-time features |
| Testing | Jest | Write meaningful unit and integration tests |
| DevOps | Docker + GitHub Actions | Build and maintain a real CI/CD pipeline |
| Monitoring | Sentry | Instrument production error tracking |

---

## 💻 Backend Setup Instructions

### Prerequisites

Ensure the following are installed on your machine before proceeding:

| Requirement | Version | Check Command | Install Guide |
|---|---|---|---|
| Node.js | 20.x LTS | `node --version` | [nodejs.org](https://nodejs.org) or `nvm install 20` |
| npm | 10.x | `npm --version` | Included with Node.js |
| Git | Any | `git --version` | [git-scm.com](https://git-scm.com) |
| Docker Desktop | Latest | `docker --version` | [docker.com](https://www.docker.com/products/docker-desktop) |

### Quick Start with Docker (Recommended)

```bash
# 1. Clone the repository
git clone https://github.com/talentswap-dev/talentswap-backend.git
cd talentswap-backend

# 2. Switch to the development branch
git checkout develop

# 3. Copy environment variable template
cp .env.example .env
# → Open .env and fill in your local values (see Environment Variables section)

# 4. Start the full local stack with Docker Compose
docker-compose up --build

# 5. In a separate terminal, run database migrations
docker exec -it talentswap_api npx prisma migrate dev

# 6. Seed the database with sample data
docker exec -it talentswap_api npx prisma db seed

# 7. Open Prisma Studio (database browser)
docker exec -it talentswap_api npx prisma studio
# → Opens at http://localhost:5555

# Verify the API is running:
curl http://localhost:3001/api/v1/health
# Expected: { "status": "ok", "timestamp": "..." }
```

### Manual Start (Without Docker)

```bash
# Prerequisites: PostgreSQL and Redis must be running locally

# 1. Clone and enter the repo
git clone https://github.com/talentswap-dev/talentswap-backend.git
cd talentswap-backend
git checkout develop

# 2. Install dependencies
npm install

# 3. Set up environment
cp .env.example .env
# Edit .env with your local database and Redis connection strings

# 4. Generate Prisma client
npx prisma generate

# 5. Run database migrations
npx prisma migrate dev

# 6. Seed the database
npx prisma db seed

# 7. Start the development server
npm run start:dev

# API available at: http://localhost:3001/api/v1
# Swagger Docs at:  http://localhost:3001/api/docs
```

---

## 🔑 Environment Variables Reference

```bash
# ─── Application ──────────────────────────────────────────────────────────────
NODE_ENV="development"                  # development | test | production
PORT=3001                               # HTTP server port
API_PREFIX="api/v1"                     # Base prefix for all routes
FRONTEND_URL="http://localhost:3000"    # Allowed CORS origin

# ─── Database (Supabase PostgreSQL) ───────────────────────────────────────────
DATABASE_URL="postgresql://user:password@host:5432/talentswap?schema=public"
DIRECT_DATABASE_URL="postgresql://user:password@host:5432/talentswap?schema=public"
# Note: DIRECT_DATABASE_URL bypasses PgBouncer for migrations

# ─── Redis ────────────────────────────────────────────────────────────────────
REDIS_URL="redis://localhost:6379"      # Redis connection string

# ─── JWT Authentication ───────────────────────────────────────────────────────
JWT_SECRET="your-long-random-secret-here"           # Access token secret
JWT_REFRESH_SECRET="another-long-random-secret"     # Refresh token secret
JWT_EXPIRY="15m"                                    # Access token expiry
JWT_REFRESH_EXPIRY="30d"                            # Refresh token expiry

# ─── Storage (Cloudflare R2) ──────────────────────────────────────────────────
R2_ACCOUNT_ID=""
R2_ACCESS_KEY_ID=""
R2_SECRET_ACCESS_KEY=""
R2_BUCKET_NAME="talentswap-uploads"
R2_PUBLIC_DOMAIN=""                     # Public CDN domain for R2 bucket

# ─── Email (Resend) ───────────────────────────────────────────────────────────
RESEND_API_KEY=""
EMAIL_FROM="noreply@talentswap.dev"

# ─── Monitoring (Sentry) ──────────────────────────────────────────────────────
SENTRY_DSN=""

# ─── AI Matching (OpenAI) ─────────────────────────────────────────────────────
OPENAI_API_KEY=""                       # Required for skill matching module

# ─── Rate Limiting ────────────────────────────────────────────────────────────
THROTTLE_TTL=60000                      # Window in ms (60 seconds)
THROTTLE_LIMIT=100                      # Max requests per window per IP
```

---

## 📜 Available Scripts

```bash
# ─── Development ──────────────────────────────────────────────────────────────
npm run start:dev       # Start with hot-reload (watch mode)
npm run start:debug     # Start with debugger attached

# ─── Production ───────────────────────────────────────────────────────────────
npm run build           # Compile TypeScript to /dist
npm run start:prod      # Run compiled production build

# ─── Code Quality ─────────────────────────────────────────────────────────────
npm run lint            # Run ESLint across all source files
npm run lint:fix        # Auto-fix ESLint violations
npm run format          # Run Prettier formatter
npm run typecheck       # Run TypeScript compiler check (no emit)

# ─── Testing ──────────────────────────────────────────────────────────────────
npm run test            # Run all unit tests
npm run test:watch      # Run unit tests in watch mode
npm run test:cov        # Run tests with coverage report
npm run test:e2e        # Run end-to-end test suite

# ─── Database ─────────────────────────────────────────────────────────────────
npm run prisma:generate     # Regenerate Prisma client after schema change
npm run prisma:migrate:dev  # Create and apply new migration (development)
npm run prisma:migrate:prod # Apply existing migrations (production)
npm run prisma:studio       # Open Prisma Studio GUI at localhost:5555
npm run prisma:seed         # Seed the database with development data
npm run prisma:reset        # ⚠️ DROPS and recreates the database (dev only)

# ─── Docker ───────────────────────────────────────────────────────────────────
npm run docker:up           # docker-compose up --build
npm run docker:down         # docker-compose down
npm run docker:logs         # Stream container logs
```

---

## 🔌 Example API Routes

### Authentication

```http
# Register a new user
POST /api/v1/auth/register
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "SecurePass123!",
  "displayName": "John Doe"
}

# Login
POST /api/v1/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "SecurePass123!"
}

# Refresh access token
POST /api/v1/auth/refresh
Content-Type: application/json

{
  "refreshToken": "eyJhbGci..."
}
```

### Skills

```http
# Create a skill listing
POST /api/v1/skills
Authorization: Bearer <access_token>
Content-Type: application/json

{
  "title": "Python Programming Basics",
  "description": "I'll teach you Python fundamentals over 3 sessions.",
  "categoryId": "clx_category_programming",
  "pointsRate": 25,
  "deliverables": "3 × 1-hour sessions, code examples, exercises",
  "tags": ["python", "programming", "beginners"]
}

# Search skill listings
GET /api/v1/skills?search=python&category=programming&page=1&limit=20
Authorization: Bearer <access_token>
```

### Wallet

```http
# Get wallet balance
GET /api/v1/wallet/balance
Authorization: Bearer <access_token>

# View transaction history
GET /api/v1/wallet/transactions?page=1&limit=20
Authorization: Bearer <access_token>
```

### Escrow

```http
# Initiate an exchange
POST /api/v1/escrow/initiate
Authorization: Bearer <access_token>
Content-Type: application/json

{
  "listingId": "clx_listing_abc123",
  "agreedDeliverables": "3 Python tutoring sessions via Discord"
}

# Confirm completion
POST /api/v1/escrow/clx_escrow_xyz789/confirm
Authorization: Bearer <access_token>
```

---

## 📬 API Response Format

All API responses follow a **standardised envelope format**:

### Success Response

```json
{
  "success": true,
  "statusCode": 200,
  "message": "Skill listing retrieved successfully.",
  "data": {
    "id": "clx_listing_abc123",
    "title": "Python Programming Basics",
    "pointsRate": 25,
    "category": {
      "id": "clx_category_programming",
      "name": "Programming",
      "slug": "programming"
    },
    "tags": ["python", "programming", "beginners"],
    "user": {
      "id": "clx_user_xyz",
      "displayName": "John Doe",
      "avatarUrl": "https://cdn.talentswap.dev/avatars/johndoe.jpg",
      "averageRating": 4.8,
      "totalExchanges": 23
    },
    "createdAt": "2025-03-15T10:00:00.000Z"
  }
}
```

### Paginated List Response

```json
{
  "success": true,
  "statusCode": 200,
  "data": [ ... ],
  "meta": {
    "total": 142,
    "page": 1,
    "limit": 20,
    "hasNextPage": true,
    "hasPreviousPage": false,
    "nextCursor": "clx_cursor_next"
  }
}
```

### Error Response

```json
{
  "success": false,
  "statusCode": 422,
  "error": "INSUFFICIENT_SKILL_POINTS",
  "message": "You need 25 SkillPoints to request this exchange, but your spendable balance is 10.",
  "timestamp": "2025-03-15T10:42:00.000Z",
  "path": "/api/v1/escrow/initiate"
}
```

---

## 🔄 Queue & Job Processing Strategy

BullMQ (built on Redis) handles all asynchronous background work:

```
Queue Architecture
──────────────────

Queue: email
  └── Job: send-verification-email     → Triggered: user registration
  └── Job: send-password-reset         → Triggered: forgot password request
  └── Job: send-exchange-summary       → Triggered: escrow completion

Queue: notifications
  └── Job: deliver-in-app-notification → Triggered: all notification events
  └── Job: push-to-websocket          → Triggered: real-time delivery

Queue: escrow-management
  └── Job: check-escrow-expiry         → Cron: every hour
  └── Job: auto-cancel-expired         → Triggered: by expiry check job
  └── Job: send-dispute-alert          → Triggered: dispute opened

Queue: ai-processing
  └── Job: generate-skill-matches      → Triggered: user requests matching
  └── Job: cache-match-results         → Triggered: after AI response

Queue: gamification
  └── Job: evaluate-badge-conditions   → Triggered: exchange completed
  └── Job: update-leaderboard          → Cron: every 10 minutes
  └── Job: award-streak-bonus          → Cron: daily at midnight

Queue: analytics
  └── Job: record-exchange-event       → Triggered: escrow state changes
  └── Job: aggregate-daily-stats       → Cron: daily at 1am
```

---

## 🌐 WebSocket Gateway Planning

```
Planned Socket.io Namespace: /ws
Authentication: JWT passed via socket.handshake.auth.token

Room Strategy:
  user:{userId}          → Personal room for private notifications
  thread:{threadId}      → Chat thread room for messaging
  presence:global        → Optional global presence tracking

Scaling Strategy:
  Redis Adapter (@socket.io/redis-adapter) planned from day 1
  Enables horizontal scaling across multiple API instances
  All Socket.io events pub/sub through Redis channels
```

---

## 📁 File Upload Architecture

```
Upload Flow (Planned)
──────────────────────
1. Client sends multipart/form-data to POST /api/v1/files/upload
2. Multer middleware validates: file type (image/jpeg, image/png, application/pdf)
   and size (max 5MB for images, max 20MB for documents)
3. File validated and temporarily stored in server memory buffer
4. AWS SDK v3 uploads buffer to Cloudflare R2 bucket
5. R2 returns the object key
6. Backend constructs and returns the public CDN URL
7. Client stores the URL in the relevant entity (profile avatar, post attachment, etc.)

Supported File Types:
  Profile avatars:   JPEG, PNG, WebP (max 5MB)
  Post attachments:  JPEG, PNG, PDF (max 10MB)
  Credential docs:   PDF, JPEG, PNG (max 20MB)

Storage Organisation:
  R2 Bucket structure:
    avatars/{userId}/{filename}
    attachments/{postId}/{filename}
    credentials/{userId}/{filename}
```

---

## 🔔 Notification System Architecture

```
Notification Trigger → NotificationsService → BullMQ Job Queue
                                                      │
                              ┌───────────────────────┤
                              │                       │
                    ┌─────────▼──────────┐  ┌─────────▼──────────┐
                    │  In-App Delivery    │  │   Email Delivery    │
                    │                    │  │                    │
                    │  1. Save to DB      │  │  1. BullMQ email   │
                    │  2. Push via        │  │     queue job      │
                    │     WebSocket to    │  │  2. Resend API     │
                    │     user room       │  │     sends email    │
                    └────────────────────┘  └────────────────────┘

Notification Types and Delivery Channels:
┌──────────────────────────┬──────────┬───────┐
│ Event                    │ In-App   │ Email │
├──────────────────────────┼──────────┼───────┤
│ Exchange Request         │   ✅     │  ✅   │
│ Exchange Accepted        │   ✅     │  ✅   │
│ Exchange Completed       │   ✅     │  ✅   │
│ SkillPoints Received     │   ✅     │  ❌   │
│ New Message              │   ✅     │  ❌   │
│ New Review               │   ✅     │  ✅   │
│ Badge Earned             │   ✅     │  ❌   │
│ Dispute Opened           │   ✅     │  ✅   │
│ Account Suspended        │   ✅     │  ✅   │
└──────────────────────────┴──────────┴───────┘
```

---

## 🛡️ Rate Limiting & Security Protections

```
Global Rate Limit (all routes):
  100 requests per 60 seconds per IP

Auth Route Rate Limits (stricter):
  POST /auth/login          → 10 requests per 15 minutes per IP
  POST /auth/register       → 5 requests per hour per IP
  POST /auth/forgot-password → 3 requests per hour per IP

AI Matching Rate Limit:
  POST /matching/find       → 10 requests per hour per user

Upload Rate Limit:
  POST /files/upload        → 20 uploads per hour per user

Additional Protections:
  ✅ Helmet.js security headers (X-Frame-Options, CSP, HSTS, etc.)
  ✅ CORS restricted to configured FRONTEND_URL
  ✅ Request body size limit: 10MB maximum
  ✅ SQL injection prevention via Prisma parameterised queries
  ✅ XSS prevention via input sanitisation
  ✅ CSRF protection for cookie-based auth flows
  ✅ Timing-safe password comparison via bcrypt
  ✅ Sensitive fields stripped from all API responses
```

---

## 🧪 Testing Strategy

### Testing Pyramid

```
         ┌───────────┐
         │  E2E Tests │       ~10% — Full request cycle from HTTP to DB
         │   (Jest)   │       Critical user flows: register, exchange, wallet
         └─────┬──────┘
         ┌─────▼──────────────┐
         │  Integration Tests  │  ~25% — Module + DB interaction
         │  (Jest + Test DB)   │  Repository layer, service dependencies
         └─────┬───────────────┘
    ┌──────────▼──────────────────────┐
    │         Unit Tests               │  ~65% — Isolated service logic
    │  (Jest + mocked dependencies)    │  Business rules, utils, validators
    └──────────────────────────────────┘
```

### Testing Standards

| Type | Tool | Target Coverage | What Is Tested |
|---|---|---|---|
| Unit | Jest + `@nestjs/testing` | 80% | Service methods, utilities, guards, pipes |
| Integration | Jest + test PostgreSQL | Key flows | Repository queries, module integration |
| E2E | Jest + Supertest | Critical paths | Auth, wallet, escrow full cycle |
| API | Thunder Client / Postman | Manual | All endpoints before PR merge |

---

## ⚡ Performance Optimization Plan

| Area | Strategy | Expected Gain |
|---|---|---|
| Database queries | Prisma query analysis + targeted indexes | 50–80% query speedup on hot paths |
| Response caching | Redis cache on high-traffic GET routes | Near-zero DB load for cached reads |
| Pagination | Cursor-based pagination instead of OFFSET | Consistent speed on large datasets |
| Payload size | Response DTOs exclude heavy/unused fields | 30–50% smaller JSON payloads |
| Async processing | BullMQ queues for non-critical operations | Immediate API response, work in background |
| Connection pooling | Supabase PgBouncer for DB connections | Handle more concurrent users |
| Compression | Gzip/Brotli on API responses | 60–80% payload compression |
| Cold starts | Keep-alive pings to Railway | Eliminate Railway cold start delays |

---

## 📦 Recommended Dependencies

### Core Production Dependencies

```json
{
  "@nestjs/common": "^10.x",
  "@nestjs/core": "^10.x",
  "@nestjs/platform-express": "^10.x",
  "@nestjs/config": "^3.x",
  "@nestjs/jwt": "^10.x",
  "@nestjs/passport": "^10.x",
  "@nestjs/throttler": "^5.x",
  "@nestjs/swagger": "^7.x",
  "@nestjs/terminus": "^10.x",
  "@nestjs/websockets": "^10.x",
  "@nestjs/platform-socket.io": "^10.x",
  "@prisma/client": "^5.x",
  "@socket.io/redis-adapter": "^8.x",
  "passport": "^0.7.x",
  "passport-jwt": "^4.x",
  "passport-local": "^1.x",
  "bcryptjs": "^2.x",
  "ioredis": "^5.x",
  "bullmq": "^5.x",
  "zod": "^3.x",
  "class-validator": "^0.14.x",
  "class-transformer": "^0.5.x",
  "multer": "^1.x",
  "@aws-sdk/client-s3": "^3.x",
  "socket.io": "^4.x",
  "@sentry/nestjs": "^8.x",
  "helmet": "^7.x",
  "compression": "^1.x"
}
```

### Core Development Dependencies

```json
{
  "@nestjs/cli": "^10.x",
  "@nestjs/testing": "^10.x",
  "prisma": "^5.x",
  "jest": "^29.x",
  "supertest": "^6.x",
  "ts-jest": "^29.x",
  "typescript": "^5.x",
  "eslint": "^8.x",
  "@typescript-eslint/eslint-plugin": "^6.x",
  "@typescript-eslint/parser": "^6.x",
  "prettier": "^3.x",
  "ts-node": "^10.x"
}
```

---

## 🤝 Contribution Guidelines

We welcome contributions from team members and the open-source community!

### How to Contribute

1. **Find a ticket** — Pick an unassigned ticket from the Linear board
2. **Create a branch** — Branch off `develop` using the naming convention
3. **Write your code** — Follow the coding standards in this README
4. **Write tests** — All new features require unit tests
5. **Open a PR** — Target `develop`, link the Linear ticket, and request review
6. **Address review feedback** — Make changes, push, and re-request review
7. **CI passes, PR merged** — Delete your branch after merge

### What We Expect in Pull Requests

- ✅ Clear PR title following commit message format
- ✅ Description explaining what changed and why
- ✅ Link to Linear ticket
- ✅ Unit tests for new business logic
- ✅ No TypeScript errors (`tsc --noEmit` passes)
- ✅ ESLint and Prettier pass
- ✅ No `console.log` statements left in code
- ✅ No secrets or credentials in code or commits

### Reporting Bugs

- Create a Linear ticket with the `bug` label
- Include: steps to reproduce, expected behaviour, actual behaviour, your environment
- For security vulnerabilities, contact the team directly rather than opening a public ticket

---

## 👥 Team Structure

| Member | Role | Primary Responsibilities |
|---|---|---|
| **Member 1** | Frontend Lead / Documentation | Frontend architecture, README, contributing guides |
| **Member 2** | Frontend Support / Design | UI components, wireframes, design system |
| **Member 3** | **Backend Lead / APIs** | NestJS modules, API design, authentication, business logic |
| **Member 4** | **Backend / DevOps / Database** | Docker, CI/CD, Prisma schema, database, Railway deployment |

---

## 🙏 Acknowledgements

This project is built on the shoulders of excellent open-source software and services:

- [**NestJS**](https://nestjs.com) — The progressive Node.js framework that makes building scalable APIs a joy
- [**Prisma**](https://prisma.io) — Next-generation ORM that makes database work type-safe and intuitive
- [**PostgreSQL**](https://postgresql.org) — The world's most advanced open-source relational database
- [**Redis**](https://redis.io) — The blazing-fast in-memory data structure store
- [**Supabase**](https://supabase.com) — Open-source Firebase alternative with a generous free tier
- [**Railway**](https://railway.app) — The easiest way to deploy backend applications
- [**Cloudflare R2**](https://cloudflare.com/products/r2) — S3-compatible object storage with zero egress fees
- [**Sentry**](https://sentry.io) — Real-time error monitoring and performance tracking
- [**BullMQ**](https://docs.bullmq.io) — Premium queue and job processing library for Node.js
- [**Socket.io**](https://socket.io) — The go-to library for real-time bidirectional communication
- [**Resend**](https://resend.com) — Modern transactional email API built for developers

---

## 📄 License

```
MIT License

Copyright (c) 2025 TalentSwap / TalentSwap Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">

---

### Built with intention. Designed to scale. Backed by community.

```
 ╔══════════════════════════════════════════════════════════════╗
 ║                                                              ║
 ║   "Skills are the new currency. Exchange freely."           ║
 ║                                                              ║
 ║                      — The TalentSwap Team                   ║
 ║                                                              ║
 ╚══════════════════════════════════════════════════════════════╝
```

**TalentSwap Backend** · Pre-Development Planning Phase · MIT License

[🐛 Report a Bug](https://github.com/talentswap-dev/talentswap-backend/issues) · [💡 Request a Feature](https://github.com/talentswap-dev/talentswap-backend/issues) · [📖 Read the Docs](http://localhost:3001/api/docs)

---

*This README was last updated during Month 1, Week 1 of the development roadmap.*  
*Implementation begins in Month 2. Architecture is subject to refinement.*

</div>
