---
name: pm-topic
description: >
  Opens, tracks and closes a short-lived topic in topics/. Use when the user
  says "open a topic", "what's in work", "close the topic", "заведи тему",
  "что у нас в работе", "закрой тему", or runs /pm-topic.
allowed-tools: Bash Read Write Edit Glob Grep
---

# Topics

A topic is a short thread of work: a launch, an investigation, a disputed
question. It has a beginning and an end. That is what separates it from the
files in `context/`, which are never closed.

## Open a topic

1. Ask why the topic is being opened and how you will know it can be closed.
   Without the second answer, don't create it — otherwise it stays open forever.
2. Create `topics/YYYY-MM-DD-name.md`:

   ```yaml
   ---
   type: topic
   date: 2026-09-19
   source: calls/2026-09-19-sync.md
   status: active
   ---
   ```

3. Fill in the sections:
   - **Why it was opened** — with a link to the source.
   - **What closes it** — a checkable condition.
   - **Already decided** — links to `decisions/`.
   - **In progress** — links to `specs/`.
   - **Open questions** — each with an owner.
   - **Log** — dates and what happened, oldest first.
4. Add a line to `index.md`, section "Current work".

## Show what is in work

1. Read `index.md` and every file in `topics/` with `status: active`.
2. For each topic show: why it was opened, what closes it, what is still open.
3. Name the topics whose last Log entry is older than a month. Ask whether they
   are still alive or ready to close.

## Close a topic

1. Ask whether the condition under "What closes it" has been met.
2. **Don't delete the file.** Set `status: done` and update `date` to the
   closing date.
3. Write the "How it ended" section and the final Log line.
4. If anything was left out of scope, name it explicitly. Either open a new
   topic or mark it `TBD`.
5. In `index.md`, move the line from "Current work" to "Closed topics".

## Rules

- Never open a topic without a closing condition.
- Never present a closed topic as current work.
- Whatever goes into a topic must cite a source.
- Don't write a long-lived fact into a topic. It belongs in `context/`.
