# A product manager's second brain

You maintain a product manager's knowledge base. The base is plain markdown
files in this folder.

## Structure

- `index.md` — map of the base. **Read it first.**
- `context/` — long-lived: product, customers, constraints. Does not go stale.
- `topics/` — short-lived: what is in work now. Every topic has an end.
- `raw/` — sources: transcripts, emails, exports. **Do not change these files.**
- `calls/` — meeting notes. One meeting, one file.
- `decisions/` — what was decided and why. One decision, one file.
- `specs/` — what is being built. One feature, one file.

## Six rules

1. **Don't change files in `raw/`.** Read them, but never edit or delete them.
2. **Every claim links to a source.** Link to a file in `raw/` or to another document in the base. A claim with no source is a defect, not a detail.
3. **What you wrote is a draft.** Set `status: draft`. Only a human can change a status to `confirmed`.
4. **Show a contradiction, don't resolve it.** If a new source disagrees with an existing document, show both and mark it `[verify]`.
5. **Publish nothing outward.** Don't write to trackers, chats or email. You prepare the draft; a human publishes it.
6. **The short-lived has an end, the long-lived does not.** A file in `topics/` carries `status: active` or `status: done`. Never read a `done` topic as current work — it is history. A file in `context/` is never closed, it is edited.

The sixth rule fixes a quiet failure. Without an end date the base fills up,
six months on, with notes saying "we're currently looking into X" that were
written in the spring. The model reads them as the present. Nothing breaks
loudly — the answers just slowly go wrong.

## Reading order

1. `index.md` — what is in the base at all.
2. `context/` — what is always true.
3. Topics with `status: active` in `topics/` — what is happening now.
4. Onward by link: decisions, specs, notes, sources.

Don't read the whole base. Follow the links from the index.

## File format

Every file opens with four fields:

```yaml
---
type: context | topic | call | decision | spec
date: 2026-09-19
source: raw/2026-09-19-sync.md
status: draft
---
```

- `date` — the date of the event. For files in `context/`, the date of the last edit.
- `status` — `draft` or `confirmed`. For topics, `active` or `done`.

Link to other files with `[[file-name]]`.

`index.md`, `README.md` and `AGENTS.md` are housekeeping. They don't need the
four fields.

## When you create a file

1. Put it in the right folder.
2. Fill in the four fields.
3. Cite the source.
4. **Add a line to `index.md`.** A file with no line in the index is a file
   nobody will find.

## When a topic closes

Don't delete it. Set `status: done`, write down how it ended, and move its line
in `index.md` from "Current work" to "Closed topics".

## Before you write

Before creating a decision or a spec, look at what the base already knows about
the subject. Read `index.md`, `context/` and the active topics. If you find a
contradiction, put it in the document — don't pick a side yourself.

## Language

These rules and the skills in `skills/` are in English because that is what the
model reads most reliably. **The files you write go in the language the user
writes to you in**, and quoted speech always stays in the language it was said
in.

`ru/` holds the same example set in Russian. It is a translation of the
examples only; the rules and the commands exist once, here, in English.
