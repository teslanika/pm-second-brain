# LinkedIn, 2026-10-07 — Second Brain basics

Published 2026-10-07 on a personal LinkedIn account. Checked against the live
post on 2026-10-13.

This is the shortest public explanation of why this repository exists: what
separates a folder from a base whose files know about their own connections.
It works as a webinar trailer, and as the text you send someone who has
installed nothing yet.

- Visual: two graph screenshots side by side — a plain folder on the left, a
  linked vault on the right.
- The text below is exactly what was published.

## What the post maps onto in this project

1. **The opening question** — "you gave your AI access to all your files, why
   are the answers still vague" — states the problem without naming a single
   tool.
2. **The frontmatter example** — a real decision record carrying `supersedes`
   and `contradicts`. It is already sanitised and published, so it can be shown
   to any room.
3. **The argument about contradiction** — two documents that disagree look
   identical in a file list; typed relations force the model to show both
   instead of averaging them. That is rule four in `AGENTS.md`, and it is the
   one thing a folder cannot do at all.

What the post leaves out and the project has: the split between long-lived and
short-lived (rule six) and `status: draft` as the default (rule three).

## The post

You gave your AI access to all your files, so why are the answers still so vague?

You have the documents. You have a decent model. And you still get back something that sounds confident, reads nicely, and that you would never put in front of a customer without checking every line yourself.

In most cases the model is doing fine with what it has. The problem is the shape of what you hand it.

Let me show you the difference, because it is smaller than most people expect.

WHAT A FOLDER ACTUALLY TELLS AN AI

Two things. The filename, and the date you saved it.

That is the whole list. Everything else that makes a document worth keeping lives in your head: who said it, what it changed, which earlier decision it cancelled, which spec it argues with.

Your AI cannot read your head, so it reads the words in the file and guesses the rest. That guess is where the vagueness comes from.

WHAT A SECOND BRAIN TELLS IT INSTEAD

A second brain is a folder where every file carries its own context. In practice that means a few lines of plain text at the top of the document.

Here is one from my own system, a record of a pricing decision:

    ---
    type: decision-record
    decision_date: 2026-10-06
    source: [[Calls/2026-10-06-Pricing-Review]]
    status: evidence
    relations:
      - type: supersedes
        target: [[Decisions/2026-07-12-Tiered-Pricing]]
      - type: contradicts
        target: [[Specs/Usage-Based-Billing-v1]]
    ---

Now look at what each line does for the model:

- type tells it this is a decision and not a draft, so it can weigh it properly
- source points at the call it came from, so every claim has something to click through to
- status says I observed this but nobody confirmed it yet, so the model can use it without treating it as settled
- supersedes says this call cancelled a decision we made back in July
- contradicts says it disagrees with a spec we have already written

Those last two lines are what a folder can never give you.

THE PART THAT ACTUALLY CHANGES THE ANSWERS

Two documents that disagree look identical in a file list. Same icon, same kind of name, both equally plausible.

An AI reading that folder will find both, pick whichever one fits your question better, and answer with total confidence. You will never learn the other one existed.

Write the disagreement into the file and the behaviour changes. The model can now tell you the two conflict, and show you both.

WHAT YOU GET OUT OF IT

- Answers arrive with sources attached, so you can verify one in about ten seconds
- Conflicts surface instead of disappearing into the average
- The reasoning behind a decision survives the quarter, which matters when somebody asks in March why you changed your mind
- It runs on plain markdown files on your laptop. No vector database, no retrieval pipeline, nothing new to buy

WHERE TO START

Please do not start by reorganising everything you own. That plan takes a weekend and dies on the Tuesday.

Pick one type of document you create often. Mine was decision records. Add five lines to the top of the next one you write, then do the same tomorrow.

So now I ask you: is your AI reading a folder, or is it reading something that knows how it is connected?

#AI #KnowledgeManagement #ProductManagement

## How LinkedIn rendered it

Worth knowing if you reuse the format:

- A leading `-` on a list item is stripped, so the four "what you get out of
  it" points read as one solid paragraph.
- The `---` fence around the frontmatter collapses, and the blank line before
  "Now look at what each line does" disappears — the example runs straight into
  the next sentence.
- Markdown bold renders literally. That is why the section headers are in caps
  rather than bold.

Prose model: Gust de Backer (gustdebacker.com). What was avoided: the negative
parallelism of "it's not X, it's Y", cataphoric teasers, chopped fragment pairs.
