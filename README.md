# A product manager's second brain

*[Русская версия](README.ru.md)*

A product manager's knowledge base in plain markdown files. Works with any
model that can read and write files: Claude Code, Cursor, Codex, Gemini CLI.

Six folders, five commands, six rules. Nothing else.

## Why

A chat forgets everything the moment you close the tab. You explain the product
again every morning. A month later nobody remembers why that decision was made.

A base in files fixes that. The files sit on your disk, you can read them with
your own eyes, and git versions them. A model plugs into them, and can be
swapped for another one at any time.

## What you need

- A markdown editor. [Obsidian](https://obsidian.md) works well — it draws the
  links between files as a graph.
- An agent that can work with files: Claude Code, Cursor, Codex or Gemini CLI.
- Git. Without it you can't roll back what the model wrote.

## Getting started

1. Clone the repository, or copy the folder.
2. Open it in Obsidian: **Open folder as vault**.
3. Open the same folder in your agent.
4. Delete the files with `example` in the name — they are a demonstration of
   the format.
5. Describe your product in `context/`, open your first topic with `/pm-topic`.
6. Drop a meeting transcript into `raw/` and run `/pm-call`.

## Structure

```
index.md     map of the base. The agent reads it first
context/     long-lived: product, customers, constraints
topics/      short-lived: what is in work now
raw/         sources: transcripts, emails, exports. Never changed
calls/       meeting notes
decisions/   what was decided and why
specs/       what is being built
```

Three more folders are not the base itself but tooling and material about it:
`skills/` with the commands, `promo/` with the texts that explain the project,
and `ru/` with the same example set in Russian. Clone it for yourself and you
can delete `promo/` and `ru/`.

## Long and short

This is the central distinction in the base, and it is worth understanding
before anything else.

**`context/` — long-lived.** What is always true about the product: who uses
it, how success is measured, what the system can't do. A file like this is
never closed. When a fact changes, the file is edited.

**`topics/` — short-lived.** A thread of work with a beginning and an end: a
launch, an investigation, a disputed question. A topic has a closing condition,
written down in advance. When the topic closes, the file gets `status: done`
and stays in the base as history.

Why split them. Without an end date, the base is full six months later of notes
saying "we're currently looking into X" that were written in the spring. The
model reads them as the present and answers confidently and wrongly. Nothing
breaks loudly — the answers just slowly rot. So the short-lived has an end, and
the long-lived does not.

## The index

`index.md` is the map of the base: long-lived files, active topics, closed
topics, decisions, specs, meetings. The agent reads it first and then follows
the links, instead of walking every folder.

The agent updates the index when it creates a file. A file that isn't in the
index is a file nobody will find.

## Commands

| Command | What it does |
|---|---|
| `/pm-setup` | creates the structure in an empty folder |
| `/pm-topic` | opens, shows and closes topics |
| `/pm-call` | turns a transcript into a note and a list of decisions |
| `/pm-spec` | builds a draft spec out of notes |
| `/pm-recall` | answers what you decided about X and how that is known |

## Six rules

The rules live in `AGENTS.md`. The agent reads them before every task.

1. **Don't change files in `raw/`.** A source stays a source.
2. **Every claim links to a source.** Without a link it isn't knowledge, it's
   a guess.
3. **What the model wrote is a draft.** A human changes the status.
4. **Show a contradiction, don't resolve it.** Two sources disagree — show both.
5. **Publish nothing outward.** The model prepares the draft, the human
   publishes.
6. **The short-lived has an end, the long-lived does not.** A closed topic is
   history, not current work.

Those six rules are the whole difference between a knowledge base and a folder
of notes you can't trust.

## What it looks like in use

Look at the files with `example` in the name. One transcript in `raw/` becomes
a note, a decision and a spec. All of it hangs off the active topic
`topics/2026-09-01-example-notifications.md`, with a closed topic next to it so
you can see how a closed one differs from a live one. The links show up in the
Obsidian graph.

## Language

`AGENTS.md` and the skills are in English, in a single copy, because that is
what the model reads most reliably. They tell the agent to write **in whatever
language you write to it in** — so a Russian-speaking PM gets a Russian base
out of an English rulebook. `ru/` holds the example set translated into
Russian, for reading; delete it if you don't need it.

## Similar projects

- [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
  by Andrej Karpathy — the original pattern.
- [second-brain](https://github.com/NicholasSpisak/second-brain) — a ready-made
  implementation of that pattern for reading and research. Installs with one
  command. Take it if what you want is a base for studying a subject rather
  than for working on a product.

## Licence

MIT. Take it, change it, use it however you like, including at work.
