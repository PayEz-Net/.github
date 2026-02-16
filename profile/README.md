# PayEz Technologies

**Enterprise Identity & Data Platform**

Production-grade infrastructure for identity management, data governance, and rapid product development. Built for compliance, designed for scale.

---

## Platform Overview

PayEz is an enterprise platform providing identity, data, and compliance infrastructure for modern applications. With 23 months of development and 1,300+ commits, our battle-tested foundation enables product launches in **5 weeks instead of 5 months** — a 4.6x acceleration over traditional development.

### Core Capabilities

**🔐 Identity & Access Management**
- Multi-tenant Identity Provider (IDP) with OAuth 2.0 / OIDC
- Two-factor authentication with TTL enforcement
- Federated identity (Microsoft, Google)
- Partner token authentication (DPoP)
- In-house JWT signing infrastructure for delegated authorization

**📊 Data & Governance**
- VibeSQL: Embedded PostgreSQL for edge computing and multi-tenant applications
- PII tokenization service within Cardholder Data Environment (CDE)
- Centralized audit trails across all sensitive operations
- Schema evolution with lazy migration on read
- Grid queries with navigation properties

**🛡️ Security & Compliance**
- Azure Key Vault + HSM integration for encryption key management
- Consolidated compliance surface area (single protected API)
- 100% audit trail coverage of sensitive operations
- RBAC with role hierarchy and platform-wide vs client-scoped permissions
- Redis-backed session management with automatic token refresh

**⚡ Developer Experience**
- Battle-tested authentication packages (Next.js, React Native)
- Agent-based development workflow
- TypeScript SDK with full type safety
- Reusable MVP packages accelerate new product launches
- Azure Kubernetes Service (AKS) deployment infrastructure

---

## Open Source Projects

We're open-sourcing key components of our platform to accelerate development for the broader community.

### VibeSQL — Production PostgreSQL, Zero Config

Full-featured PostgreSQL 16 that runs anywhere. **Currently powering 3 production sites** including idealresume.online, idealvibe.online, and internal infrastructure. Embedded in your binary or deployed as a multi-tenant server.

| Project | Description | Status |
|---------|-------------|--------|
| [vibesql-micro](https://github.com/PayEz-Net/vibesql-micro) | Single-binary embedded PostgreSQL 16 with HTTP API | ✅ Production |
| [vibesql-server](https://github.com/PayEz-Net/vibesql-server) | Multi-tenant server with schema evolution (.NET 9) | ✅ Production |
| [vibesql-edge](https://github.com/PayEz-Net/vibesql-edge) | Auth gateway — bring your own IDP to VibeSQL (.NET 9) | ✅ Production |
| [vibesql-audit](https://github.com/PayEz-Net/vibesql-audit) | PCI DSS audit logging — PostgreSQL C extension + Rust forwarder | ✅ Production |
| [vibesql-vault](https://github.com/PayEz-Net/vibesql-vault) | Governed storage for encrypted data — access policies, retention, purge proof (Rust) | 🚀 Development |
| [vibe-sdk](https://github.com/PayEz-Net/vibe-sdk) | Automatic ORM - typed classes generated from your schema, zero config | ✅ Stable |

**Why VibeSQL?**
- **Full-fledged relational database** — Complete PostgreSQL 16, not a subset
- **Production-proven** — Running live sites with real users and revenue
- **Zero dependencies** — No PostgreSQL installation required
- **HTTP-native** — REST API for SQL, no database drivers needed
- **Schema evolution** — Lazy migration on read with declarative transforms
- **Multi-tenant ready** — Isolated data per client with tier-based limits
- **AI-agent friendly** — Autonomous installation and operation
- **Cross-platform** — Windows, macOS, Linux (amd64/arm64)

```bash
# One command to run PostgreSQL
./vibesql-micro serve

# Query via HTTP
curl -X POST http://localhost:5173/v1/query \
  -H "Content-Type: application/json" \
  -d '{"sql": "SELECT * FROM users WHERE age > 25"}'
```

**Vibe SDK — The ORM That Disappears**

The entire ORM layer, automated and invisible. Change your VibeSQL schema, save the file — your TypeScript types update automatically. No build step, no commands, no configuration. **It just works.**

- **Live hot-reload** — Polls for schema changes every 10 seconds, regenerates types automatically
- **Zero configuration** — No Prisma schema, no TypeORM decorators, no migration scripts
- **Full type safety** — Your VibeSQL schema becomes typed TypeScript classes
- **Pre-built everything** — CRUD operations, React hooks, server components
- **Invisible infrastructure** — So reliable you forget it's running

**The entire ORM layer is automated.** Connect your Next.js app to VibeSQL and your types just... exist. Update your schema? Types update. Add a collection? New types appear. It's one of those things that just always works, so you never think about it.

```typescript
// No ORM config needed. Just use it.
import { useVibeCollection } from '@vibe/client/react';

export function ProductList() {
  const { data, isLoading } = useVibeCollection('products');
  // 'data' is fully typed from your VibeSQL schema
  return <div>{data?.map(p => <div key={p.id}>{p.name}</div>)}</div>;
}
```

### Authentication & Identity SDKs

Production-ready authentication packages extracted from our platform. Battle-tested with 2FA, session management, and type-safe API clients.

| Project | Description | Status |
|---------|-------------|--------|
| [payez-next-mvp](https://github.com/PayEz-Net/payez-next-mvp) | Next.js auth with NextAuth.js, Zustand, 2FA, RBAC | ✅ Production |
| [payez-react-native-mvp](https://github.com/PayEz-Net/payez-react-native-mvp) | React Native auth with biometric support & type-safe clients | ✅ Production |

**Features:**
- Session sync between NextAuth and Zustand
- Two-factor authentication flow (SMS, email, authenticator)
- Token refresh with automatic retry
- PII redaction in logs
- Role-based access control with hierarchy
- Generic error codes (no internal details exposed)
- Redis session storage for scalability

---

## Platform Architecture

### Production Infrastructure

Our platform runs on Azure with enterprise-grade security and compliance:

- **Azure Kubernetes Service (AKS)** — Container orchestration
- **Azure Key Vault + HSM** — Hardware-backed encryption key management
- **Azure DevOps** — CI/CD pipelines with automated testing
- **Redis** — Distributed session management
- **PostgreSQL** — Primary data store with JSONB support

### Compliance & Security

**Consolidated Compliance Surface Area**
- All PII tokenization flows through a single protected API within the Cardholder Data Environment (CDE)
- Encryption key management centralized to Azure Key Vault with HSM backing
- 100% audit trail coverage of sensitive operations
- Unified logging, access control, and encryption at rest/in transit

**Previous:** Multiple systems touching sensitive data, each requiring separate compliance documentation.
**Now:** Centralized through PayEz-Core with unified security controls.

---

## Platform Maturity

### By the Numbers

| Metric | Value | Insight |
|--------|-------|---------|
| **Development Time** | 23 months | Core platform (Jan 2024 - Present) |
| **Total Commits** | 1,300+ | Stable, battle-tested foundation |
| **Source Files** | 1,777 | Comprehensive feature coverage |
| **Time to Production** | 5 weeks | New products on PayEz infrastructure |
| **Speed Improvement** | 4.6x | Faster than traditional development |
| **IDP Completion** | 100% | Production-deployed |

### Recent Launches

- **idealresume.online** — AI-powered resume analysis (GPT-4) with Stripe payments. **Zero to revenue in 5 weeks.**
- **idealvibe.online** — VibeSQL showcase with AI schema designer
- **Nexus.CryptAply** — Enterprise key management portal (Azure Marketplace, Q2 2026 target)

---

## What We Build

PayEz accelerates product development for:

- **Fintech Applications** — PCI-compliant infrastructure with built-in tokenization
- **SaaS Platforms** — Multi-tenant identity and data management out of the box
- **Enterprise Tools** — Governance, compliance, and audit trails from day one
- **AI Agents** — Autonomous installation and operation with VibeSQL
- **Developer Tools** — Reusable auth, identity, and data patterns

---

## Technology Stack

**Backend:** .NET 9.0, ASP.NET Core, Entity Framework Core 9.0
**Frontend:** Next.js 15, React 19, TypeScript, TailwindCSS
**Mobile:** React Native, .NET MAUI
**Data:** PostgreSQL 16, Redis, JSONB
**Auth:** OAuth 2.0, OIDC, DPoP, NextAuth.js
**Infrastructure:** Azure (AKS, Key Vault, DevOps)
**Security:** HSM-backed keys, PII tokenization, audit logging

---

## Platform API

Production infrastructure at **[api.payez.net](https://api.payez.net)**

- **Identity Provider** — OAuth 2.0 / OIDC with multi-tenant support
- **Vibe Data API** — CRUD, Grid queries, navigation properties
- **Payment Processing** — PCI-compliant transaction handling
- **Partner Tokens** — Delegated authorization with DPoP
- **Agent Collaboration** — Tools for autonomous agent workflows

---

## Get Started

**Explore Open Source:**
- Try [VibeSQL Micro](https://github.com/PayEz-Net/vibesql-micro) for embedded PostgreSQL
- Use [PayEz Next.js MVP](https://github.com/PayEz-Net/payez-next-mvp) for rapid auth implementation
- Build with [Vibe SDK](https://github.com/PayEz-Net/vibe-sdk) for type-safe data access

**Production Platform:**
- Contact: **developers@payez.net**
- Website: **[payez.net](https://payez.net)**

---

## Vision

We believe infrastructure should accelerate, not slow down product development. PayEz provides the identity, data, and compliance foundation that lets teams focus on building products instead of rebuilding the same security and governance patterns.

**Enterprise-grade infrastructure. Developer-friendly experience. Open source where it matters.**

---

*Built with grit in the USA* 🇺🇸

**PayEz Technologies** | Enterprise Identity & Data Platform
