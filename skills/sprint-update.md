---
name: sprint-update
description: End-of-sprint documentation update ritual
---

Perform the end-of-sprint documentation update based on work completed in this conversation.

## Step 1: Read Current State

Read these files:
- SPRINTS.md
- CLAUDE.md

If it exists, also read:
- docs/PRODUCT-DECISIONS.md

## Step 2: Analyze Conversation Context

Review the current conversation to identify:
- Tasks completed this session
- New product/technical decisions made
- Any blockers encountered
- Files created or modified

Do NOT ask the user what was completed - you have full context from this conversation.

## Step 3: Update SPRINTS.md

Based on conversation context:
- Mark completed tasks with [x]
- Move incomplete tasks to "In Progress" or "Up Next"
- Add any new blockers with description
- Update sprint status if complete (🟡 → ✅)
- If sprint complete, update next sprint status to 🟡 In Progress

## Step 4: Update PRODUCT-DECISIONS.md (if applicable)

If new decisions were made during this session:
- Add them to the appropriate section
- Include date and brief rationale
- Keep format consistent with existing entries

## Step 5: Update Handoff Prompt

Update the "Current Handoff Prompt" section in SPRINTS.md with:
- Current sprint number and status
- Updated completed items list
- Updated next steps
- Any blockers noted

## Step 6: Update CLAUDE.md

Update the sprint roadmap section to reflect current status.

## Step 7: Summary

Show the user a brief summary:
- Files updated
- Tasks marked complete
- Current sprint status
- Next steps for upcoming work

Keep all updates minimal and focused. Don't add unnecessary content or formatting.
