# Claude Sprint Manager

**Slash commands and templates for managing sprints with Claude Code**

A lightweight framework for tracking sprints, handoffs, and project documentation when working with Claude Code (Anthropic's CLI assistant).

## Why This Exists

When working with AI assistants on multi-sprint projects, context gets lost between chat sessions. This framework solves that with:

- **Structured sprint tracking** in a single SPRINTS.md file
- **Handoff prompts** that capture current state for new chats
- **Slash commands** to automate sprint updates and handoffs
- **Templates** that work with any tech stack

## Quick Start

### 1. Install the Slash Commands

Copy the skills to your Claude config directory:

```bash
# Create skills directory if it doesn't exist
mkdir -p ~/.claude/skills

# Copy the skills
cp skills/sprint-handoff.md ~/.claude/skills/
cp skills/sprint-update.md ~/.claude/skills/
```

### 2. Add Templates to Your Project

Copy the templates to your project root:

```bash
cp templates/SPRINTS.md your-project/
cp templates/CLAUDE-SPRINT-SECTION.md your-project/  # Or merge into existing CLAUDE.md
```

### 3. Use the Commands

| Command | When | What It Does |
|---------|------|--------------|
| `/sprint-update` | End of sprint | Reviews progress, updates docs, marks tasks complete |
| `/sprint-handoff` | Starting new chat | Generates context prompt for seamless continuation |

## File Structure

```
claude-sprint-manager/
├── README.md                 # This file
├── skills/
│   ├── sprint-handoff.md     # Generates handoff prompts
│   └── sprint-update.md      # End-of-sprint doc updates
├── templates/
│   ├── SPRINTS.md            # Full sprint tracking template
│   └── CLAUDE-SPRINT-SECTION.md  # Sprint section for CLAUDE.md
└── examples/
    └── signalstream/         # Real-world example
        ├── SPRINTS.md
        └── CLAUDE.md
```

## How It Works

### The Sprint Cycle

```
┌─────────────────────────────────────────────────────────┐
│                     SPRINT CYCLE                        │
├─────────────────────────────────────────────────────────┤
│                                                         │
│   1. START SPRINT                                       │
│      └── Use handoff prompt or /sprint-handoff          │
│                                                         │
│   2. WORK ON TASKS                                      │
│      └── Claude reads CLAUDE.md + SPRINTS.md            │
│                                                         │
│   3. END SPRINT                                         │
│      └── Run /sprint-update                             │
│          - Mark completed tasks                         │
│          - Document new decisions                       │
│          - Update handoff prompt                        │
│                                                         │
│   4. NEW CHAT                                           │
│      └── Paste handoff prompt or /sprint-handoff        │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Key Concepts

**SPRINTS.md** — Single source of truth for sprint status
- Epic overview
- Per-sprint task checklists
- Definition of done criteria
- Current handoff prompt (always up to date)

**Handoff Prompt** — Context blob for new chats
- Current sprint and status
- What's done, in progress, blocked
- Key files to read
- Copy-paste ready

**Slash Commands** — Automation for the ritual
- `/sprint-update` enforces the end-of-sprint checklist
- `/sprint-handoff` generates fresh context from current state

## Templates

### SPRINTS.md Structure

```markdown
# Project Sprint Planning

## Overview
| Epic | Sprints | Goal | Status |
|------|---------|------|--------|
| Epic 1 | 1-2 | Foundation | 🟡 In Progress |
| Epic 2 | 3-4 | Core Features | ⚪ Not Started |

## Sprint 1: Foundation ← CURRENT
**Goal**: [Clear goal statement]
**Status**: 🟡 In Progress

### Completed ✅
- [x] Task 1
- [x] Task 2

### In Progress 🔄
- [ ] Task 3

### Up Next 📋
- [ ] Task 4

### Definition of Done
- [ ] Criteria 1
- [ ] Criteria 2

---

## Sprint Handoff

### Current Handoff Prompt
[Copy-paste prompt here]
```

### Status Indicators

| Icon | Meaning |
|------|---------|
| 🟡 | In Progress |
| ✅ | Complete |
| ⚪ | Not Started |
| 🔴 | Blocked |

## Best Practices

### End of Every Sprint
1. Run `/sprint-update`
2. Review and confirm task completion
3. Document any new decisions
4. Verify handoff prompt is current

### Starting New Chats
1. Either paste the handoff prompt from SPRINTS.md
2. Or run `/sprint-handoff` to generate fresh prompt
3. Ask Claude to read CLAUDE.md and SPRINTS.md

### Keeping Docs in Sync
- Update SPRINTS.md as you complete tasks (not just at sprint end)
- Add product decisions to PRODUCT-DECISIONS.md immediately
- Keep handoff prompt updated after significant progress

## Customization

### Adapting for Your Project

The templates use generic placeholders. Customize:

1. **Epic structure** — 2-4 epics works well for most projects
2. **Sprint length** — Templates assume ~1 week sprints
3. **Task granularity** — Break into 2-4 hour chunks
4. **Definition of done** — Add your team's quality gates

### Adding More Skills

Create new skills in `~/.claude/skills/`:

```markdown
---
name: your-skill-name
description: What it does
---

Instructions for Claude...
```

## About Skylark 118

[Skylark 118](https://github.com/skylark118) is an AI consultancy sharing practical frameworks for building with AI. Our open-source tools focus on what actually works in production.

**Other frameworks:**
- [data-steward-agent](https://github.com/skylark118/data-steward-agent) — Data governance framework for SaaS

## Contributing

Issues and PRs welcome at [github.com/skylark118/claude-sprint-manager](https://github.com/skylark118/claude-sprint-manager)

## License

MIT — Use freely, attribution appreciated.
