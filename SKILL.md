---
name: calibrate
version: 1.0
updated: 2026-04-14
description: In-session self-improvement. Reviews the current conversation for corrections, preferences, and patterns, then suggests specific skill/setup updates. Triggers on "calibrate", "what can you improve", "update your skills", "what did we learn", "tune up".
---

# Calibrate: In-Session Self-Improvement

## What This Does

Reviews the current conversation and suggests specific updates to skills, CLAUDE.md rules, memory, or workflows based on what just happened. Jay picks which suggestions to apply.

## When to Use

- End of a work session
- After a task with multiple corrections
- When Jay says "calibrate", "what can you improve", "tune up", "update your skills"

## Process

### Step 1: Scan the Conversation

Review everything in the current session. Look for:

- **Corrections** — where the user said "no", "wrong", "not that", "I meant X"
- **Preferences revealed** — format choices, tone adjustments, workflow preferences
- **Process gaps** — steps you missed that a skill should encode
- **Repeated patterns** — same type of correction more than once = systemic issue
- **Things that worked** — approaches the user confirmed or accepted without pushback

### Step 2: Match to Updateable Targets

For each finding, identify WHERE the fix belongs:

- **Skill file** — if the issue is about how a specific task is executed
- **CLAUDE.md** — if the issue is about general agent behavior or rules
- **Memory** — if it's a preference or context that should persist across sessions
- **Workflow/cron** — if it's about when or how automated tasks run
- **SOUL.md / persona file** — if it's about tone or writing style (rare, check with the user)

### Step 3: Present Suggestions

Format as a numbered list. Each suggestion should be:

```
[number]. [TARGET: filename] — [what to change]
Brief why: [one sentence explaining the pattern that triggered this]
```

Example:
```
1. SKILL: thumbnail-skill — Add rule to always generate 3 thumbnail variations, not 1
Brief why: You asked for alternatives twice this session after I gave a single option.

2. CLAUDE.md — Add "never suggest routing to other agents" to red lines
Brief why: You corrected me when I suggested handing off to another agent.

3. MEMORY — Save preference: user prefers kebab-case for all file names
Brief why: You renamed two files I created in camelCase.
```

Rules for suggestions:
- **Max 7 suggestions.** If you find more, prioritize by impact (repeated corrections > one-offs).
- **Be specific.** Not "improve writing quality" but "add rule: no sentences over 20 words in community posts."
- **Only suggest changes the data supports.** Don't pad with generic improvements.
- **If nothing meaningful to update, say so.** "Clean session — nothing to calibrate" is a valid output.

### Step 4: Apply

Wait for the user to respond with which numbers to apply (e.g. "do 1 and 3", "all", "skip 2").

Then:
1. Make the changes to the target files
2. Confirm each change with the file path and a one-line summary
3. If updating a skill, re-read it after editing to verify it's coherent
4. If updating memory, follow the memory system rules (write file + update MEMORY.md index)

### Step 5: Done

No follow-up needed. Changes are live for the next time the skill/rule is invoked.

## What NOT to Suggest

- Changes that are already in the relevant skill or CLAUDE.md (check first)
- Generic "best practices" not grounded in this session's data
- Temporary fixes for one-off situations
- Changes to other agents' files unless this agent has write access
