---
name: pm-recall
description: >
  Answers what the team decided about a subject and how that is known. Use
  when the user asks "what did we decide about X", "why did we do it this
  way", "что мы решили про X", "почему мы так сделали", or runs /pm-recall.
allowed-tools: Bash Read Glob Grep
---

# Recall a decision

## Steps

1. Read `index.md`. Then follow the links; don't walk every folder.
2. Collect what relates to the subject: files in `context/`, topics in
   `topics/`, then `decisions/`, `specs/` and `calls/`.
3. Read what you found.
4. Answer briefly: what was decided, when, and on what basis.
5. Give every claim a `[[file-name]]` link.
6. If two documents disagree, show both and say which is newer. Don't choose
   for the person.
7. If you found nothing, say so. Don't assemble an answer out of guesses.

## Rules

- Write nothing. This skill only reads.
- Never give an answer without links.
- Present a `status: done` topic as history: "closed on this date, this way."
  Don't pass it off as current work.
- If a long-lived file in `context/` disagrees with an active topic, show both
  and say which is newer.
