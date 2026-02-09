# PayEz.Net

**Building the future of embedded databases and payment infrastructure.**

---

## VibeSQL

Our flagship open-source project — PostgreSQL that runs anywhere, zero-config.

| Project | Description | Status |
|---------|-------------|--------|
| [vibesql-micro](https://github.com/PayEz-Net/vibesql-micro) | Single-binary embedded PostgreSQL with HTTP API | ✅ Ready |
| [vibesql-server](https://github.com/PayEz-Net/vibesql-server) | Multi-tenant PostgreSQL server with schema evolution | ✅ Ready |

### Why VibeSQL?

- **Zero dependencies** — PostgreSQL embedded in your app binary
- **HTTP-native** — REST API for SQL, no drivers needed
- **AI-agent friendly** — Designed for autonomous installation and operation
- **Cross-platform** — Windows, macOS, Linux (amd64/arm64)

```bash
# One command to run PostgreSQL
./vibesql-micro serve

# Query via HTTP
curl -X POST http://localhost:5173/v1/query \
  -H "Content-Type: application/json" \
  -d '{"sql": "SELECT 1 + 1 as answer"}'
```

---

## About PayEz

PayEz powers secure payment processing and identity management for businesses. Our infrastructure handles millions of transactions with enterprise-grade security.

- 🔐 **Identity Provider** — OAuth 2.0 / OIDC with RBAC
- 💳 **Payment Processing** — PCI-compliant transaction handling
- 🛡️ **Security First** — DPoP, key rotation, MFA

---

## Connect

- 🌐 [payez.net](https://payez.net)
- 📧 Contact: developers@payez.net

---

*Built with grit in the USA* 🇺🇸
