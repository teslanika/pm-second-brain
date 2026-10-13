---
name: pm-setup
description: >
  Creates the structure of a product manager's second brain in an empty
  folder. Use when the user says "set up my PM vault", "create a second
  brain", "настрой базу", "создай второй мозг", or runs /pm-setup.
allowed-tools: Bash Read Write Glob
---

# Set up the base

## Steps

1. Ask which folder the base goes in. Offer the current one.
2. Create the folders `context/`, `topics/`, `raw/`, `calls/`, `decisions/`, `specs/`.
3. Copy `AGENTS.md` from this skill into the root of the base.
4. Create `index.md` — the map of the base. Sections: long-lived, current work,
   closed topics, decisions, specs, meetings. Empty for now.
5. Ask which agents the person uses. Create a pointer to `AGENTS.md` for each:
   - Claude Code — `CLAUDE.md`
   - Cursor — `.cursor/rules/pm-second-brain.mdc`
   - Gemini CLI — `GEMINI.md`
   - Codex — `AGENTS.md` already works
6. Offer to run `git init` and make the first commit.
7. Show what was created and name the next step: describe the product in
   `context/` and open the first topic with `/pm-topic`.

## If the folder is not empty

Overwrite nothing. Say which files already exist and ask what to do.
