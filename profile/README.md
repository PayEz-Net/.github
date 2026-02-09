# PayEz.Net

**Building the future of embedded databases and payment infrastructure.**

---

## Open Source Projects

### VibeSQL

PostgreSQL that runs anywhere, zero-config. Our flagship open-source database project.

| Project | Description | Status |
|---------|-------------|--------|
| [vibesql-micro](https://github.com/PayEz-Net/vibesql-micro) | Single-binary embedded PostgreSQL with HTTP API | ✅ Ready |
| [vibesql-server](https://github.com/PayEz-Net/vibesql-server) | Multi-tenant PostgreSQL server with schema evolution | ✅ Ready |
| [vibe-sdk](https://github.com/PayEz-Net/vibe-sdk) | TypeScript SDK with Next.js integration | ✅ Ready |

**Why VibeSQL?** Zero dependencies • HTTP-native • AI-agent friendly • Cross-platform

```bash
# One command to run PostgreSQL
./vibesql-micro serve

# Query via HTTP
curl -X POST http://localhost:5173/v1/query \
  -H "Content-Type: application/json" \
  -d '{"sql": "SELECT 1 + 1 as answer"}'
```

### Developer Tools

Battle-tested authentication packages for rapid development:

| Project | Description | Status |
|---------|-------------|--------|
| [payez-next-mvp](https://github.com/PayEz-Net/payez-next-mvp) | Next.js auth package with 2FA & session management | ✅ Ready |
| [payez-react-native-mvp](https://github.com/PayEz-Net/payez-react-native-mvp) | React Native auth with type-safe API clients | ✅ Ready |

---

## About PayEz

PayEz powers secure payment processing and identity management for businesses. Our production infrastructure at [api.payez.net](https://api.payez.net) handles millions of transactions with enterprise-grade security.

**Platform:**
- 🔐 **Identity Provider** — OAuth 2.0 / OIDC with RBAC at api.payez.net
- 💳 **Payment API** — PCI-compliant transaction processing
- 🛡️ **Security First** — DPoP, key rotation, MFA, HSM integration

**What We Do:**
We build infrastructure for fintech, payment processors, and developers who need production-grade auth and data solutions without the complexity.

---

## Connect

- 🌐 [payez.net](https://payez.net)
- 📧 Contact: developers@payez.net

---

*Built with grit in the USA* 🇺🇸
