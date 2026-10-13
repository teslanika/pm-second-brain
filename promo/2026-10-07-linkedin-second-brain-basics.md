# LinkedIn, 2026-10-07 — Second Brain basics

Опубликовано 2026-10-07 в личном LinkedIn. Сверено с живым постом 2026-10-13.

Это самое короткое публичное объяснение того, зачем нужен этот репозиторий:
чем папка отличается от базы, у которой файлы знают про свои связи. Годится как
анонс вебинара и как текст, которым можно объяснить проект человеку, который
ещё ничего не ставил.

- Визуал: две картинки графа рядом — слева обычная папка, справа связанный vault.
- Текст ниже — ровно то, что было опубликовано.

## Что из поста ложится прямо в проект

1. **Открывающий вопрос** — «вы дали ИИ доступ ко всем файлам, почему ответы
   всё ещё расплывчатые» — ставит проблему, не называя ни одного инструмента.
2. **Пример фронтматтера** — настоящая запись решения с `supersedes` и
   `contradicts`. Он уже санитизирован и опубликован, так что его можно
   показывать любому залу.
3. **Аргумент про противоречие** — два спорящих документа в списке файлов
   выглядят одинаково; типизированные связи заставляют модель показать оба
   вместо того, чтобы усреднить. Это четвёртое правило из `AGENTS.md`, и это
   единственное, чего папка не умеет в принципе.

Чего в посте нет и что в проекте есть: разделение долгого и короткого
(шестое правило) и `status: draft` как умолчание (третье).

## Текст поста

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

## Как это отрисовал LinkedIn

Полезно знать, если будешь переиспользовать формат:

- Ведущий `-` у списков срезается, поэтому четыре пункта «что ты получаешь»
  читаются сплошным абзацем.
- Рамка `---` вокруг фронтматтера схлопывается, а пустая строка перед
  «Now look at what each line does» исчезает — пример упирается прямо
  в следующее предложение.
- Markdown-жирный отрисовывается буквально. Поэтому заголовки разделов
  набраны капсом, а не болдом.

Стилевой образец прозы: Gust de Backer (gustdebacker.com). Чего избегали:
негативного параллелизма «it's not X, it's Y», катафорических завлекалок,
рубленых пар-фрагментов.
