# SignalStream Sprint Planning

**Quick reference for sprint status and task tracking**

*This is a real-world example from the SignalStream project — a Reddit channel listening app.*

---

## Overview

| Epic | Sprints | Goal | Status |
|------|---------|------|--------|
| **Epic 1** | Sprint 1-2 | Foundation & Data Pipeline | 🟡 In Progress |
| **Epic 2** | Sprint 3-4 | Intelligence Layer | ⚪ Not Started |
| **Epic 3** | Sprint 5-6 | Dashboard & Polish | ⚪ Not Started |

---

## Epic 1: Foundation & Data Pipeline

*Get data flowing from Reddit → Database → Dashboard*

### Sprint 1: Foundation & Infrastructure ← CURRENT

**Goal**: Project runs locally with working auth and database

**Status**: 🟡 In Progress

#### Completed ✅
- [x] Project structure set up
- [x] package.json and config files created
- [x] Dependencies installed (`npm install`)
- [x] Build and lint passing
- [x] Database types defined (`lib/supabase/database.types.ts`)
- [x] .env.local template created
- [x] Product decisions documented (`docs/PRODUCT-DECISIONS.md`)
- [x] Folder structure organized
- [x] Cron route placeholders created
- [x] Lib subfolders created (reddit, ai, slack, validations)

#### In Progress 🔄
- [ ] Set up Supabase project (cloud)
- [ ] Deploy database schema (SQL in setup guide)
- [ ] Add Supabase credentials to .env.local
- [ ] Seed BlueRock client data

#### Up Next 📋
- [ ] Wire Supabase auth to login/signup forms
- [ ] Test authentication flow (signup → login → dashboard → logout)
- [ ] Update dashboard overview with placeholder content

#### Definition of Done
- [ ] Can create account and log in
- [ ] Dashboard visible after login
- [ ] BlueRock data visible in Supabase
- [ ] `npm run build` passes ✅
- [ ] `npm run lint` passes ✅

---

### Sprint 2: Reddit Integration

**Goal**: Collect Reddit posts matching BlueRock's keywords

**Status**: ⚪ Not Started

#### Tasks
- [ ] Create Reddit API client (`lib/reddit/client.ts`)
- [ ] Implement keyword matching logic
- [ ] Build scoring algorithm (relevance + engagement + velocity)
- [ ] Create daily collection cron job
- [ ] Build basic feed page
- [ ] Create PostCard component
- [ ] Add FeedFilters component
- [ ] Add post status management (new/reviewed/archived)
- [ ] Test end-to-end collection flow

#### Key Files
```
lib/reddit/client.ts          # Reddit API auth & fetching
lib/reddit/scoring.ts         # Post scoring algorithm
app/api/cron/daily-collect/route.ts
app/(dashboard)/feed/page.tsx
components/dashboard/PostCard.tsx
```

#### Definition of Done
- [ ] Reddit API successfully fetching posts
- [ ] Posts stored in Supabase with scores
- [ ] Feed page displays posts with filters
- [ ] Cron job runs without errors

---

## Epic 2: Intelligence Layer

*Add AI-powered insights and notifications*

### Sprint 3: AI Insight Extraction

**Goal**: Extract actionable insights from posts using Claude

**Status**: ⚪ Not Started

#### Tasks
- [ ] Create Claude client using Vercel AI SDK
- [ ] Design insight extraction prompt
- [ ] Build extraction function with structured output
- [ ] Add insights to collection pipeline
- [ ] Display insights on post cards
- [ ] Create insights aggregation page
- [ ] Handle rate limiting and errors

---

### Sprint 4: Slack Notifications

**Goal**: Deliver daily digests and weekly summaries via Slack

**Status**: ⚪ Not Started

#### Tasks
- [ ] Create Slack webhook client
- [ ] Design daily digest message format
- [ ] Build daily digest cron job
- [ ] Design weekly summary prompt (Claude)
- [ ] Build weekly summary cron job
- [ ] Store weekly summaries in database
- [ ] Create weekly summaries page
- [ ] Create Slack settings page

---

## Epic 3: Dashboard & Polish

*Make it useful and delightful*

### Sprint 5: Analytics Dashboard

**Goal**: Build useful overview and aggregation views

**Status**: ⚪ Not Started

#### Tasks
- [ ] Design dashboard overview metrics
- [ ] Build stat cards with real data
- [ ] Create trend charts
- [ ] Build insights aggregation page
- [ ] Add date range filters
- [ ] Add export functionality (CSV)

---

### Sprint 6: Settings & Deploy

**Goal**: Complete settings UI and deploy to production

**Status**: ⚪ Not Started

#### Tasks
- [ ] Build sources settings page
- [ ] Build keywords settings page
- [ ] Build general settings page
- [ ] Set up Vercel deployment
- [ ] Configure Vercel Cron
- [ ] Final testing and polish

---

## Links

- **Project Hub**: [CLAUDE.md](CLAUDE.md)
- **Product Decisions**: [docs/PRODUCT-DECISIONS.md](docs/PRODUCT-DECISIONS.md)

---

## Sprint Handoff

### End-of-Sprint Checklist

Before starting a new chat, update these files:
1. **SPRINTS.md** — Mark completed tasks, update status
2. **docs/PRODUCT-DECISIONS.md** — Add any new decisions made
3. **Handoff Prompt below** — Update with current state

Or run: `/sprint-update`

### Current Handoff Prompt

Copy this into a new Claude Code chat to continue work:

```
I'm continuing work on SignalStream, a Reddit channel listening app.

**Current Status**: Sprint 1 (Foundation) - In Progress

**What's Done**:
- Project structure, dependencies, build passing
- Database types defined, .env.local template ready
- Product decisions documented
- Cron route placeholders created

**What's Next**:
- Set up Supabase cloud project
- Deploy database schema
- Add credentials to .env.local
- Seed BlueRock client data
- Wire auth to login/signup forms
- Test authentication flow

**Key Files**:
- CLAUDE.md - Project hub
- SPRINTS.md - Sprint tracking
- docs/PRODUCT-DECISIONS.md - Product specs
- lib/supabase/database.types.ts - DB schema

Please read CLAUDE.md and SPRINTS.md to understand the project, then help me continue Sprint 1.
```

---

*Last Updated: January 2, 2025*
