---
name: sprint-handoff
description: Generate a sprint handoff prompt for seamless chat continuation
---

Read the following files in the current project:
- SPRINTS.md (current sprint status)
- CLAUDE.md (project context)

If it exists, also read:
- docs/PRODUCT-DECISIONS.md (recent decisions)

Based on the current state, generate a **handoff prompt** that can be copied into a new Claude Code chat.

The handoff prompt should include:

1. **Project name and one-line description**
2. **Current sprint** — number, name, and status (In Progress/Blocked/Complete)
3. **What's completed** — bullet list of done items from current sprint
4. **What's in progress** — any partially done work
5. **What's blocked** — any blockers and why (or "None")
6. **What's next** — immediate next steps
7. **Key files to read** — the most important files for context

Format the output as a code block that can be directly copied.

Example format:

```
I'm continuing work on [Project], a [description].

**Current Status**: Sprint X ([Name]) - [Status]

**Completed**:
- Item 1
- Item 2

**In Progress**:
- Item being worked on

**Blocked**:
- None

**Next Steps**:
- Step 1
- Step 2

**Key Files**:
- CLAUDE.md - Project hub
- SPRINTS.md - Sprint tracking

Please read CLAUDE.md and SPRINTS.md, then help me continue.
```

After generating, offer to update the "Current Handoff Prompt" section in SPRINTS.md with the new prompt.
