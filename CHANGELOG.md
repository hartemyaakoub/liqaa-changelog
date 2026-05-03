# LIQAA Cloud — public changelog

What's new across the LIQAA platform — API, SDKs, console, infrastructure.
Format follows [Keep a Changelog](https://keepachangelog.com).

For SDK-specific changes, see each repo's `CHANGELOG.md`:
- [@liqaa/js](https://github.com/hartemyaakoub/liqaa-js/blob/main/CHANGELOG.md)
- [liqaa-php](https://github.com/hartemyaakoub/liqaa-php/blob/main/CHANGELOG.md)
- [liqaa-python](https://github.com/hartemyaakoub/liqaa-python/blob/main/CHANGELOG.md)
- [liqaa-go](https://github.com/hartemyaakoub/liqaa-go/blob/main/CHANGELOG.md)

---

## [2026-05-03]

### Added
- **MCP server (`@liqaa/mcp`)** — let AI agents (Claude Desktop, Cursor, Continue) start video calls via the Model Context Protocol. Supports `liqaa_create_room`, `liqaa_issue_sdk_token`, webhook management, plus live docs as MCP resources.
- **Polyglot SDKs** — official server-side SDKs for **PHP** (Composer), **Python** (PyPI), and **Go** (`go get`). Same API surface as the JS SDK.
- **OpenAPI 3.1 spec** — published at [`hartemyaakoub/liqaa-openapi`](https://github.com/hartemyaakoub/liqaa-openapi). Generate clients in 50+ languages via `openapi-generator`.
- **`Awesome LIQAA`** list — curated index of SDKs, integrations, and community resources.
- Public **roadmap** repo.

### Changed
- Homepage redesigned to a Stripe-grade layout with animated network hero + flowing architecture diagram.
- `/learn` developer catalog launched — 7 sections, 12 framework guides, 8 use cases, 6 core concepts, production checklist.
- All marketing pages unified under one `<SiteHeader>` / `<SiteFooter>` (Geist + Geist Mono typography).

### Security
- HMAC-signed webhooks now use a 5-minute replay window (was 10).
- CSP tightened on all marketing pages — no inline scripts in critical paths.

---

## [2026-05-02]

### Added
- **TKAWEN ID single sign-on** — enterprise identity via Authentik OIDC, available on `/auth/oidc/redirect`.
- **Google OAuth** restored as a first-class login option.
- Direct-call URLs (`?name=…&auto=1`) for cross-platform integrations — no more "type your name" lobby when called from Algeria Certify.

### Fixed
- Frontend was building with `localhost:8000` baked into chunks (env precedence bug). All builds now pin `https://liqaa.io/api`.
- Static dashboard pages were stuck in dark theme; unified across the entire app.

---

## [2026-05-01]

### Added
- **Self-serve console** at `/console` — issue API keys, view usage, manage webhooks, see billing.
- **Marketing site v1.0** — landing, pricing, docs, signup, login, status.
- Status page at `/status` with real-time health checks across API, SDK, console, signaling, and recording.

### Infrastructure
- LIQAA Cloud now runs on dedicated bare-metal in EU + MENA edge.
- All systems behind nginx with HTTP/2 + HSTS preload.

---

## [2026-04-30]

### Added — initial public release
- Public beta of the **LIQAA JS SDK** at `https://liqaa.io/sdk.js` (6.4 KB gzipped).
- **REST API** — `/api/public/v1/` with conversations, sdk-token, webhooks endpoints.
- **HMAC-signed webhooks** with exponential backoff retry (1, 2, 4, 8, 16s).
- **WebRTC infrastructure** — LiveKit SFU mesh with simulcast (3 layers) and adaptive bitrate.
- **Persistent rooms** — same conversation = same room across calls.
- npm packages: `@liqaa/js`, `@liqaa/react`.

---

## Subscribe

- ⭐ Star [`hartemyaakoub/liqaa-changelog`](https://github.com/hartemyaakoub/liqaa-changelog) and watch releases for an RSS-friendly feed.
- 📧 We post major releases on [LinkedIn](https://linkedin.com/in/hartem-yaakoub) and [@liqaa_io](https://x.com/liqaa_io).
- 🟢 [status.liqaa.io](https://liqaa.io/status) for live infra health.
