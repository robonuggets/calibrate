# calibrate

In-session self-improvement skill for Claude Code (or any agent harness that supports skills).

Reviews the current conversation for corrections, preferences, and patterns, then suggests specific updates to your skills, CLAUDE.md, memory, or workflows. You pick which suggestions to apply.

## Triggers

`calibrate`, `what can you improve`, `update your skills`, `what did we learn`, `tune up`

## Install

Drop `SKILL.md` into your skills directory:

- **Project-level:** `.claude/skills/calibrate/SKILL.md`
- **User-level:** `~/.claude/skills/calibrate/SKILL.md`

That's it. Invoke by typing `calibrate` (or any of the trigger phrases) at the end of a session.

## What it does

1. Scans the current conversation for corrections, preferences, gaps, and patterns
2. Maps each finding to a target file (skill, CLAUDE.md, memory, workflow)
3. Presents up to 7 specific suggestions
4. Applies the ones you pick

## License

MIT
