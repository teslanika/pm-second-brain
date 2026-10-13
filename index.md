# Map of the base

The entry point. The agent reads this file first and then follows the links,
instead of walking every folder.

## Long-lived

What is always true about the product. These files are never closed — they are
edited.

| File | About |
|---|---|
| [[example-product]] | product, roles, metrics |
| [[example-customers]] | customers and what they keep asking for |

## Current work

Topics with `status: active`.

| Topic | Opened | What closes it |
|---|---|---|
| [[2026-09-01-example-notifications]] | 2026-09-01 | counter in production, tickets falling for two weeks |

## Closed topics

History. Do not read as current work.

| Topic | Closed | How it ended |
|---|---|---|
| [[2026-06-15-example-course-search]] | 2026-07-20 | course search shipped to production |

## Decisions

| Decision | Date | Status |
|---|---|---|
| [[2026-09-15-example-push-deferred]] | 2026-09-15 | draft |

## Specs

| Spec | Status |
|---|---|
| [[example-unread-badge]] | draft |

## Meetings

| Note | Source |
|---|---|
| [[2026-09-15-example-weekly-sync]] | [[2026-09-15-example-weekly-sync-transcript]] |

## Housekeeping

- [[AGENTS]] — the rules the agent reads before every task.
- [[README]] — why this exists and what the commands are.

`inbox/` is not in the index either. It is a queue, not knowledge: files sit
there until `/pm-inbox` sorts them, and then the line appears here. In the
graph they show up as loose dots with no links — which is exactly what
unsorted material is.

The skills in `skills/` are tools, not knowledge. They are not in the index,
and the graph hides them with the filter `-path:skills`. There is one list of
commands and it lives in the README.

`ru/` holds the same example set in Russian. It is a translation of the
examples only — the rules and the commands exist once, in English, at the root.
Delete the folder if you don't need it.

## How to use this

Reading order: index → `context/` → active topics → onward by link.

The agent updates the index when it creates a file. A file with no line in the
index barely exists as far as the base is concerned: nobody will find it.
