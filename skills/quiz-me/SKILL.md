---
name: quiz-me
description: Quiz the user on anything until they truly understand it — a page, a doc, code, a concept, or what was just discussed. One question at a time, with choices plus answering in their own words; wrong answers get a step-by-step explanation and a retry later. Use when the user says "quiz me", "test me", "make sure I understand", "check what stuck", or "test my understanding".
argument-hint: <what to quiz on>
---

# Quiz me

Goal: the user deeply understands how something works **today**. Not trivia. Not fixes.

What it does not do: explain the topic up front, save progress between sessions, or schedule repeats.

## Before anything

Load these skills:

1. `i-have-adhd:i-have-adhd`: when installed, every word this skill produces follows it: each question, each piece of feedback, the final recap. Missing? Go on, and keep the same shape: answer first, short sentences, numbered steps, no preamble.
2. `fp-thinking`: how to explain a wrong answer. Missing? Go on, and still explain in cause-and-effect steps.

## 1. Find the source

The quiz checks the user against something real. Pick it in this order:

1. What the user named: a page, file, doc, link, or topic.
2. Nothing named? What was just explained or built in this conversation.
3. Still unclear? Ask one question: "Quiz you on what?"

Read the whole source before writing any question. For a bare topic with no material, check the facts (docs, code, a run) before you quiz on them.

## 2. Pick the ideas

1. Pull 5 to 8 ideas, in cause-and-effect order: each one builds on the one before.
2. Before the first question, show: how the quiz works (5 short lines), the idea list (more than 5? group them), and "Score: 0 of N solid".

## 3. Quiz

One question per `AskUserQuestion` call.

### Writing a question

- Ask how it works today. Never ask the user to pick or judge fixes.
- Ask why, not trivia: no file names, line numbers, or numbers to memorize. Prefer small stories: "this happens. Why?"
- 3 or 4 options: one right, the rest common wrong ideas. Move the right one around, never mark it. Multi-select only for "which of these are true today?"
- The question stands alone, since the user may see only the dialog. Start with "Idea 3 of 8."
- Say that typing in their own words counts extra. The tool adds the typing box itself.

### Scoring

- An idea is solid after 2 right answers. At least one is in their own words or on a new story.
- Own words that hit the core count as right. Add the missing detail in 1 or 2 lines.
- Every turn, show the score: "5 of 8 solid. Idea 6 at 1 of 2."

### Wrong or half right

Before telling the user they're wrong, check the claim against the source. A wrong correction is the worst thing this skill can do.

1. Say what was right first, in one line.
2. Walk to the right answer in numbered steps, fp-thinking style. Use real evidence (runs, numbers, screenshots) when there is any.
3. Two ideas mixed up? Show a 2-row table: which question each one answers.
4. Ask the idea again later with a new story, never the same question.

### User says they don't get the question

That's the question's fault. Explain the idea behind it with an everyday example, then ask a simpler version.

### User adds their own question to an answer

Grade the answer, then answer their question from the source (a table often works), then go on.

### User pushes back with their own theory

1. Grant what's true in it.
2. Show the evidence that points elsewhere.
3. Ask a narrower question that tests only the missing piece.

## 4. Finish

When every idea is solid, or the user says stop:

1. The whole chain, built from the user's own words.
2. Where they needed retries, one line each: "you said X, it's Y."
3. Questions that were badly written, named as your fault.

## Rules

- Never show the answer before they answer.
- No fixes, plans, or code during the quiz. The user wants those? That's a separate task after.
- No praise padding. "Right." Then the detail.
