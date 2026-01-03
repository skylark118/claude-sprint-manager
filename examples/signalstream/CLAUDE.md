# CLAUDE.md - SignalStream Project Hub

**Guidance for Claude Code and AI assistants working with this project**

*This is a real-world example — a Reddit channel listening app with AI insights.*

---

## PROJECT OVERVIEW

**Project**: SignalStream
**Description**: Channel listening web app that monitors Reddit for market intelligence
**Status**: In Development
**First Client**: BlueRock (agentic security startup)

**Tech Stack**:
- Next.js 14 App Router, TypeScript
- Tailwind CSS, shadcn/ui, Skylark 118 design tokens
- Supabase (PostgreSQL + Auth)
- Claude API via Vercel AI SDK
- Vercel (hosting + cron), Slack Webhooks

---

## CRITICAL RULES (NON-NEGOTIABLE)

### Security (Supabase)
- **NO localStorage** for auth — cookies only
- **NO client-side mutations** — use Server Actions
- **RLS enabled** on ALL tables
- **Zod validation** on ALL inputs (server-side)
- **Service role key** only in API routes/cron jobs

### Accessibility (Skylark 118)
- **NO red/green** color combinations
- **Always** use: color + shape + text for status
- Blue = positive, Orange = negative

### Code Quality
- Explicit return types on all functions
- Server Components by default
- Always handle errors with try/catch
- Always check Supabase errors: `if (error) throw error`

### Before Completion
```bash
npm run build  # Must pass
npm run lint   # Must pass
# Manual test in browser required
```

---

## SPRINT ROADMAP

**Full sprint details**: [SPRINTS.md](SPRINTS.md)

| Epic | Sprints | Focus | Status |
|------|---------|-------|--------|
| **Epic 1** | 1-2 | Foundation & Data Pipeline | 🟡 Sprint 1 |
| **Epic 2** | 3-4 | Intelligence Layer (AI + Slack) | ⚪ Pending |
| **Epic 3** | 5-6 | Dashboard & Polish | ⚪ Pending |

### Current: Sprint 1 — Foundation

**Goal**: Project runs locally with working auth and database

| Status | Task |
|--------|------|
| ✅ | Project structure, configs, dependencies |
| ✅ | Build & lint passing |
| ✅ | Database types, .env.local, product decisions |
| 🔄 | Set up Supabase, deploy schema, seed BlueRock |
| ⚪ | Wire auth, test login flow |

**Done when**: Can sign up, log in, see dashboard, BlueRock in database

---

## PROJECT STRUCTURE

```
signalstream/
├── app/
│   ├── globals.css              ← Design tokens
│   ├── layout.tsx               ← Root layout
│   ├── (marketing)/page.tsx     ← Landing
│   ├── auth/                    ← Login/signup
│   ├── (dashboard)/             ← Protected routes
│   └── api/cron/                ← Scheduled jobs
├── components/
│   ├── ui/                      ← shadcn components
│   ├── dashboard/               ← Dashboard components
│   └── forms/                   ← Form components
├── lib/
│   ├── supabase/                ← DB clients & types
│   ├── reddit/                  ← Reddit API
│   ├── ai/                      ← Claude integration
│   ├── slack/                   ← Slack webhooks
│   └── validations/             ← Zod schemas
├── actions/                     ← Server Actions
├── docs/                        ← Documentation
├── middleware.ts                ← Auth middleware
└── CLAUDE.md                    ← This file
```

---

## DATABASE SCHEMA

| Table | Purpose |
|-------|---------|
| `clients` | Multi-tenant configuration |
| `subreddit_configs` | Subreddits to monitor |
| `keywords` | Required/boost/exclude keywords |
| `posts` | Collected Reddit posts |
| `insights` | AI-extracted insights |
| `weekly_summaries` | Weekly AI summaries |
| `job_logs` | Cron execution logs |

---

## KEY DOCUMENTATION

| Document | Purpose |
|----------|---------|
| [SPRINTS.md](SPRINTS.md) | Sprint tracking & handoff |
| [docs/PRODUCT-DECISIONS.md](docs/PRODUCT-DECISIONS.md) | Product & tech decisions |

---

*Last Updated: January 2, 2025*
