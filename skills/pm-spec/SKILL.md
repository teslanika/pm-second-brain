---
name: pm-spec
description: >
  Builds a draft spec out of notes and decisions. Use when the user says
  "draft a spec", "pull the requirements together", "напиши спеку",
  "собери требования", or runs /pm-spec.
allowed-tools: Bash Read Write Edit Glob Grep
---

# Draft spec

## Before you write

Find what the base already knows about the subject. In order: `index.md`,
`context/`, the active topics in `topics/`, then `decisions/` and `specs/`.
If you find a contradiction, put it in the spec and mark it `[verify]`.
Don't pick a side yourself.

Read a closed topic (`status: done`) as history, not as current requirements.

## Steps

1. Ask which feature the spec is for, if that isn't clear.
2. Gather the sources: notes in `calls/`, decisions in `decisions/`.
3. Create a file in `specs/`:

   ```yaml
   ---
   type: spec
   date: 2026-09-19
   source: calls/2026-09-19-sync.md
   status: draft
   ---
   ```

4. Fill in the sections:
   - **Problem** — what problem is being solved and whose it is.
   - **In scope** — the boundary of the work.
   - **Out of scope** — what is deliberately left out.
   - **How we know it is done** — checkable conditions.
   - **Risks**
   - **Open questions** — each with an owner or a next step.
   - **Sources** — `[[file-name]]` links to everything this grew from.
5. Put a note at the top of the body: draft, needs review.
6. Add the spec to `index.md` and to the "In progress" section of its topic.

## Rules

- Never write a claim without a source.
- Mark an inference as one. Don't pass it off as the customer's words.
- If the evidence is thin, write an open question rather than plausible text.
