---
type: decision
date: 2026-09-15
source: raw/2026-09-15-example-weekly-sync-transcript.md
status: draft
---

# Defer push, ship the counter now

> Draft. A human changes the status, not the agent.

## What was decided

The unread counter in the messages section ships this quarter. Push
notifications are deferred, not before December 2026.

## Why

- Push requires standing up the iOS notification service — about three weeks
  of work. [source: Boris, [[2026-09-15-example-weekly-sync]]]
- The counter is two days; the data already reaches the client.
  [source: Boris, [[2026-09-15-example-weekly-sync]]]
- Support estimates the counter removes half the tickets.
  [source: Vera, [[2026-09-15-example-weekly-sync]]]

## What this contradicts

**The customer was given a different date.** Anna's email to Lanterna of
20 August 2026, item 1: "Push notifications for new messages from a teacher —
November." This decision moves them to December at the earliest.
[source: raw/2026-08-20-example-lanterna-email.md]

The unread counter covers part of the same need, but it is not what was
promised. **There is no email to the customer about the change in the
sources.** `[verify]`

## Who decided

Anna, product. Recorded at the meeting.

## What happens next

Spec: [[example-unread-badge]]
