---
name: sprint-handoff
description: Generate a sprint handoff prompt for seamless chat continuation
---

Generate a handoff prompt based on the current project state.

## Step 1: Read Project Files

Read these files in the current project:
- SPRINTS.md (current sprint status)
- CLAUDE.md (project context)

If it exists, also read:
- docs/PRODUCT-DECISIONS.md (recent decisions)

## Step 2: Generate Handoff Prompt

Create a concise handoff prompt that includes:

1. **Project name and one-line description**
2. **Current sprint** — number, name, and status
3. **What's completed** — bullet list of done items (recent sprints)
4. **What's blocked** — any blockers and why (or "None")
5. **What's next** — immediate next steps from current sprint tasks
6. **Key files to read** — the most important files for context

Format as a code block that can be directly copied into a new chat.

## Step 3: Output and Update

1. Display the generated handoff prompt in a code block
2. Automatically update the "Current Handoff Prompt" section in SPRINTS.md with the new prompt

Example format:

```
I'm continuing work on [Project], a [description].

**Current Status**: Sprint X ([Name]) - [Status]

**Completed**:
- Sprint 1: [summary]
- Sprint 2: [summary]

**Blocked**:
- [blocker] or "None"

**Next Steps**:
1. First task
2. Second task

**Key Files**:
- CLAUDE.md - Project hub
- SPRINTS.md - Sprint tracking
- [other relevant files]

Please read CLAUDE.md and SPRINTS.md, then help me continue with [specific next task].
```
