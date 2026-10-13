---
name: pm-call
description: >
  Turns a meeting transcript into a note and a list of decisions. Use when
  the user has put a file in raw/ and asks to process the meeting, says
  "process this call", "разбери звонок", "обработай встречу", or runs
  /pm-call.
allowed-tools: Bash Read Write Edit Glob Grep
---

# Process a meeting

## Steps

1. Read `index.md` and the active topics in `topics/` to work out what the
   meeting relates to.
2. Read the file in `raw/` in full.
3. Name the 3–5 main takeaways and ask which matter and which to drop. Wait
   for the answer.
4. Create a note in `calls/` with the same name as the source:

   ```yaml
   ---
   type: call
   date: 2026-09-19
   source: raw/2026-09-19-sync.md
   status: draft
   ---
   ```

   Then: who was there, what was discussed, what was decided, what was left open.
5. For each decision create a separate file in `decisions/`: what was decided,
   why, and how it is known.
6. Link the files with `[[file-name]]`.
7. Add a line to the "Log" section of the topic the meeting relates to.
   If no topic fits, offer to open one with `/pm-topic`.
8. Add the new files to `index.md`.
9. Report back: how many files you created and what questions are still open.

## Rules

- Don't change the file in `raw/`.
- Every claim carries a link to its source.
- Don't invent what isn't in the transcript. Write an open question instead.
- Leave quoted speech in the language it was said in.
- A fact that is true always, not just this week, should be offered for
  `context/`. Don't write there yourself without confirmation.
