---
name: sprint-update
description: End-of-sprint documentation update ritual
---

Perform the end-of-sprint documentation update:

## Step 1: Read Current State

Read these files:
- SPRINTS.md
- CLAUDE.md

If it exists, also read:
- docs/PRODUCT-DECISIONS.md

## Step 2: Review Sprint Progress

Ask the user:
1. "What tasks did we complete this sprint?"
2. "Any new product/technical decisions to document?"
3. "Any blockers or issues to note for next sprint?"

Wait for user response before proceeding.

## Step 3: Update SPRINTS.md

Based on user input:
- Mark completed tasks with [x]
- Move incomplete tasks to "In Progress" or "Up Next"
- Add any new blockers with description
- Update sprint status if complete (🟡 → ✅)
- If sprint complete, update next sprint status to 🟡 In Progress

## Step 4: Update PRODUCT-DECISIONS.md (if applicable)

If user mentioned new decisions:
- Add them to the appropriate section
- Include date and brief rationale
- Keep format consistent with existing entries

## Step 5: Generate New Handoff Prompt

Update the "Current Handoff Prompt" section in SPRINTS.md with:
- Current sprint number and status
- Updated completed items list
- Updated next steps
- Any blockers noted

## Step 6: Summary

Show the user a brief summary:
- Files updated
- Tasks marked complete
- Current sprint status
- Next steps for upcoming work

Keep all updates minimal and focused. Don't add unnecessary content or formatting.
