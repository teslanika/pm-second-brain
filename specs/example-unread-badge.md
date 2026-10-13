---
type: spec
date: 2026-09-15
source: calls/2026-09-15-example-weekly-sync.md
status: draft
---

# Unread message counter

> Draft. Written by the agent, needs review.

## Problem

Users don't see new messages from teachers and reply days late. Thirty-four
support tickets in two weeks.
[source: Vera, [[2026-09-15-example-weekly-sync]]]

## In scope

Show the number of unread messages on the section icon. The data already
reaches the client. [source: Boris, [[2026-09-15-example-weekly-sync]]]

## Out of scope

Push notifications. Deferred by a separate decision:
[[2026-09-15-example-push-deferred]]

## How we know it is done

- The number on the icon matches the count of unread messages.
- Opening the section resets the number to zero.
- Support tickets on this subject fall. Threshold not agreed. `[verify]`

## Risks

If the counter doesn't reset on open it sits there permanently and stops
working as a signal. [source: Boris, [[2026-09-15-example-weekly-sync]]]

## Open questions

- What to show above 99? Owner: Anna, will ask design.
- Success threshold on support tickets. Owner: unassigned. `TBD`

## Sources

- [[2026-09-15-example-weekly-sync]]
- [[2026-09-15-example-push-deferred]]
