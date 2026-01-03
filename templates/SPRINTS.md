# [PROJECT_NAME] Sprint Planning

**Quick reference for sprint status and task tracking**

---

## Overview

| Epic | Sprints | Goal | Status |
|------|---------|------|--------|
| **Epic 1** | Sprint 1-2 | [Foundation/Setup] | 🟡 In Progress |
| **Epic 2** | Sprint 3-4 | [Core Features] | ⚪ Not Started |
| **Epic 3** | Sprint 5-6 | [Polish/Deploy] | ⚪ Not Started |

---

## Epic 1: [Epic Name]

*[One-line description of what this epic delivers]*

### Sprint 1: [Sprint Name] ← CURRENT

**Goal**: [Clear, measurable goal]

**Status**: 🟡 In Progress

#### Completed ✅
- [x] Example completed task
- [ ] <!-- Add completed tasks here -->

#### In Progress 🔄
- [ ] Current task being worked on

#### Up Next 📋
- [ ] Next task
- [ ] Following task

#### Definition of Done
- [ ] Criterion 1 (e.g., "Build passes")
- [ ] Criterion 2 (e.g., "Feature works in browser")
- [ ] Criterion 3 (e.g., "Tests written")

---

### Sprint 2: [Sprint Name]

**Goal**: [Clear, measurable goal]

**Status**: ⚪ Not Started

#### Tasks
- [ ] Task 1
- [ ] Task 2
- [ ] Task 3

#### Key Files
```
path/to/file1.ts
path/to/file2.ts
```

#### Definition of Done
- [ ] Criterion 1
- [ ] Criterion 2

---

## Epic 2: [Epic Name]

*[One-line description]*

### Sprint 3: [Sprint Name]

**Goal**: [Goal]

**Status**: ⚪ Not Started

#### Tasks
- [ ] Task 1
- [ ] Task 2

---

### Sprint 4: [Sprint Name]

**Goal**: [Goal]

**Status**: ⚪ Not Started

#### Tasks
- [ ] Task 1
- [ ] Task 2

---

## Epic 3: [Epic Name]

*[One-line description]*

### Sprint 5: [Sprint Name]

**Goal**: [Goal]

**Status**: ⚪ Not Started

#### Tasks
- [ ] Task 1
- [ ] Task 2

---

### Sprint 6: [Sprint Name]

**Goal**: [Goal]

**Status**: ⚪ Not Started

#### Tasks
- [ ] Task 1
- [ ] Task 2

---

## Quick Commands

```bash
# Development
npm run dev              # Start dev server
npm run build            # Production build
npm run lint             # Run linter

# Add project-specific commands here
```

---

## Links

- **Project Hub**: [CLAUDE.md](CLAUDE.md)
- **Product Decisions**: [docs/PRODUCT-DECISIONS.md](docs/PRODUCT-DECISIONS.md)

---

## Sprint Handoff

### End-of-Sprint Checklist

Before starting a new chat, update these files:
1. **SPRINTS.md** — Mark completed tasks, update status
2. **PRODUCT-DECISIONS.md** — Add any new decisions made
3. **Handoff Prompt below** — Update with current state

Or run: `/sprint-update`

### Current Handoff Prompt

Copy this into a new Claude Code chat to continue work:

```
I'm continuing work on [PROJECT_NAME], a [one-line description].

**Current Status**: Sprint 1 ([Sprint Name]) - In Progress

**What's Done**:
- Initial setup complete
- [Add completed items]

**What's Next**:
- [Next task 1]
- [Next task 2]

**Key Files**:
- CLAUDE.md - Project hub
- SPRINTS.md - Sprint tracking

Please read CLAUDE.md and SPRINTS.md to understand the project, then help me continue.
```

---

*Last Updated: [DATE]*
