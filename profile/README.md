# PayEz Technologies

**Open source auth, database, and payment infrastructure** — extracted from a PCI-compliant payment platform. Drop in what you need. Leave what you don't.

---

## 🚀 Drop-In MVPs — Start Here

Open source. MIT licensed. Use them however you want — commercial, personal, remix, fork. The MVPs connect to **[idp.payez.net](https://api.payez.net)** for identity and **[VibeSQL](https://vibesql.online)** for data. 10K MAU free. No credit card.

| Project | What You Get | Install |
|---------|-------------|---------|
| **[@payez/next-mvp](https://github.com/PayEz-Net/payez-next-mvp)** | Full-stack auth for Next.js — login, signup, 2FA, sessions, RBAC, OAuth, Stripe billing | `npm install @payez/next-mvp` |
| **[payez-react-native-mvp](https://github.com/PayEz-Net/payez-react-native-mvp)** | Native mobile auth — biometrics, deep linking, Zustand, automatic token refresh | `git clone` |
| **[vibe-sdk](https://github.com/PayEz-Net/vibe-sdk)** | Auto-generated TypeScript ORM from your VibeSQL schema. Zero config. | `npm install @vibe/sdk` |

**What's included in every MVP:**
- NextAuth.js / Zustand session sync
- Two-factor authentication (SMS, email, TOTP)
- Role-based access control with hierarchy
- Custom schemas that foreign-key to real users
- Redis distributed sessions
- AI agent scaffolding & customization ready

```bash
# Next.js: Zero to login screen in under 10 minutes
npm install @payez/next-mvp
# Set 4 env vars → done.
```

---

## 📊 VibeSQL — Production PostgreSQL, Zero Config

Full PostgreSQL 16 over HTTP. No drivers, no connection strings. Embedded in your binary or deployed as a multi-tenant server. **Currently powering 3 production sites** including idealresume.online and idealvibe.online.

| Project | Description | Status |
|---------|-------------|--------|
| [vibesql-micro](https://github.com/PayEz-Net/vibesql-micro) | Single-binary embedded PostgreSQL 16 with HTTP API | ✅ Production |
| [vibesql-server](https://github.com/PayEz-Net/vibesql-server) | Multi-tenant server with schema evolution (.NET 9) | ✅ Production |
| [vibesql-edge](https://github.com/PayEz-Net/vibesql-edge) | Auth gateway — bring your own IDP to VibeSQL (.NET 9) | ✅ Production |
| [vibesql-audit](https://github.com/PayEz-Net/vibesql-audit) | PCI DSS audit logging — PostgreSQL C extension + Rust forwarder | ✅ Production |
| [vibesql-vault](https://github.com/PayEz-Net/vibesql-vault) | Governed storage for encrypted data (Rust) | 🚀 Development |
| [vibesql-cryptaply](https://github.com/PayEz-Net/vibesql-cryptaply) | CryptAply encryption plugin — governed key lifecycle (Rust) | 🚀 Development |
| [vibesql-backup](https://github.com/PayEz-Net/vibesql-backup) | Encrypted backup pipeline (Rust) | 🚀 Development |
| [vibesql-sync](https://github.com/PayEz-Net/vibesql-sync) | Governed replication with signed audit trail (Rust) | 🚀 Development |

```bash
# One command to run PostgreSQL
./vibesql-micro serve

# Query via HTTP — any language, any agent
curl -X POST http://localhost:5173/v1/query \
  -H "Content-Type: application/json" \
  -d '{"sql": "SELECT * FROM users WHERE age > 25"}'
```

**Docs:** [vibesql.online](https://vibesql.online/docs.html)

---

## 🔐 Platform Services

The MVPs are free — the platform behind them is how we keep the lights on.

| Service | What It Does |
|---------|-------------|
| **[idp.](https://api.payez.net)** | Identity Provider — OAuth 2.0 / OIDC, multi-tenant, 2FA, SSO |
| **[cloud.](https://api.payez.net)** | Payment API — cards, ACH, vaulting, Stripe subscriptions, PCI-compliant |
| **[cryptaply.](https://cryptaply.com)** | Key Management — HSM-backed signing key rotation via Azure Key Vault |
| **[vibesql](https://vibesql.online)** | Managed PostgreSQL — your custom schemas, our infrastructure |

**Pricing:** 10K MAU free → Pro $49/mo → Business $199/mo → Enterprise custom
**No SSO tax.** 100K MAU + 3 SSO connections for $199/mo.

---

## Get Started

1. `npm install @payez/next-mvp` — or clone the React Native MVP
2. Set 4 env vars (CLIENT_ID, IDP_URL, etc.)
3. First login screen in under 10 minutes
4. Add custom schemas with VibeSQL — they foreign-key to your users automatically

**Website:** [api.payez.net](https://api.payez.net) · **Docs:** [vibesql.online](https://vibesql.online/docs.html) · **Contact:** developers@payez.net

---

*Built with grit in the USA* 🇺🇸
