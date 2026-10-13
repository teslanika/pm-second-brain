---
name: pm-inbox
description: >
  Sorts whatever has been dumped into inbox/ into the right folders of the
  base. Use when the user says "process the inbox", "sort my files", "I
  copied my downloads in", "разбери inbox", "разбери папку", "я скинул сюда
  файлы", or runs /pm-inbox.
allowed-tools: Bash Read Write Edit Glob Grep
---

# Process the inbox

`inbox/` is a queue, not a store. Things land there unsorted and leave typed.
`raw/` is the opposite: once a source is there it stays forever and is never
edited.

Most people come to this with years of material already on disk. They do not
reorganise it — they copy it in and let the base absorb what matters.

## Work in three passes. Never skip the second.

### 1. Scan

Read every file in `inbox/`, including subfolders. Do not write, move, rename
or delete anything in this pass.

For each file work out: what kind of thing it is, what date it belongs to, and
whether it is product material at all.

Some files you cannot read — archives, installers, video, binaries. Don't
guess at their contents from the filename.

### 2. Show the plan and wait

Show a table — file, what you think it is, where it would go, why — grouped by
outcome, with counts. Then stop and wait for an answer.

The person may say "that one's not what you think" or "leave that alone". That
is the point of the pass.

### 3. Execute

Only what was agreed, and only after the answer.

## The four outcomes

| Outcome | What you do |
|---|---|
| **Source** — transcript, email, export, a document someone else wrote | Move it to `raw/`. Then write the document it supports: a note in `calls/`, a fact in `context/`, a decision in `decisions/`. The new document cites the file in `raw/`. |
| **Derived** — something you can summarise but whose original is not worth keeping | Write the document in the right folder, cite where it came from, move the original to `raw/` anyway if it is the only evidence. |
| **Unclear** | Leave it in `inbox/` and ask one specific question about it. Never invent a type to empty the queue. |
| **Not product material** | Leave it exactly where it is. Say that you left it and why, in one line. Do not open it, do not copy it, do not describe its contents. |

## Personal material

People's folders contain their private life. Bank statements, tickets,
passports, photos, medical documents, contracts that are not yours to read.

When a file looks like that, it falls under "not product material". Name it by
filename only — never by content — and move on. If you are unsure whether
something is private, treat it as private and ask.

## After the queue

1. Compare what you just wrote against each other and against the base. Where
   two documents disagree, say so, show both and mark the claim `[verify]`.
   Don't pick a side — a contradiction found at this moment is the most
   valuable thing in the batch.
2. Add every new file to `index.md`.
3. Report: how many files, split by outcome; what is still in `inbox/` and
   what you need to know about it; which contradictions you found.

## Rules

- Nothing is deleted. Ever. Files move inside the base or stay where they are.
- Nothing leaves the base. You do not publish, send or upload anything.
- Never edit a file after it has landed in `raw/`.
- A document with no `source` is a defect. Write the link or don't write the
  document.
- Everything you write is `status: draft`.
- Don't empty the queue for the sake of emptying it. Three files understood
  are worth more than thirty files filed wrongly.
