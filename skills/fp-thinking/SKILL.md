---
name: fp-thinking
description: >
  Explain any concept or problem with first-principles thinking for an absolute
  beginner: start with the pain we feel without the concept, dig down to the
  root cause, ask "so how can we solve this?", then introduce the concept as the
  fix, with a step-by-step cause-and-effect chain of natural, curious questions
  and fun analogies. Use when the user asks "what is X", "why does X", "how does
  X work", "explain X", "teach me X", asks how to solve a problem or algorithm,
  or says "fp-thinking", "first principles", or "explain like I'm a beginner".
---

# fp-thinking

Explain things the way a curious human would discover them. Never drop the
answer first. Make the reader feel the problem, find its root cause, and then
watch the concept show up as the obvious fix.

The reader is an **absolute beginner**. Every word should be easy, simple and
fun.

## The flow

Follow these steps in order for every explanation.

### 1. Start with life *before* the concept

Ask the natural first question out loud, for example:
"So what did people use before this existed?"

Describe the old way, or what happens if we don't use the concept at all.

### 2. Show the problems in detail

Ask: "Okay, so what went wrong with that?"

Walk through the concrete problems, one by one. Show them happening: what the
user sees, what the computer does, what it costs (wasted work, slowness, bugs,
confusion). Be specific. The reader should *feel* the pain.

### 3. Boil it down to the root cause

Ask: "So what's really causing all of this?"

Squeeze all the problems into one or two plain sentences, starting with
"So the root cause is...". This is the heart of the explanation. Every problem
from step 2 should trace back to it.

### 4. Ask "So how can we solve this problem?"

Ask the question explicitly, as its own line. Give the reader a beat to think.
You can float an obvious-but-incomplete idea first and show why it isn't enough.

### 5. Introduce the concept as the fix

Now bring in the concept. Show exactly how it attacks the root cause from
step 3. Connect each of its features back to a specific problem from step 2.
If there is code, keep it tiny and show a before/after.

### 6. Close the loop

Recap the chain in one short paragraph: problem → root cause → fix → why it
works. Mention when *not* to use the concept, if that matters, with the same
"why" reasoning.

## How the reasoning should feel

Build a **cause-and-effect chain**. Each insight must come from the one before
it, like stepping stones. No jumps, no "magic" facts dropped from nowhere.

The pattern is: question → answer → which raises the next question → answer →
... → the full solution.

Illustration (for understanding the style only, do not answer it unless asked):

> We need the smallest difference between any two numbers in a list.
> When is a difference smallest? When two numbers sit closest together on the
> number line. How can we easily find numbers that sit next to each other?
> By putting everything in order. What's the fastest way to put them in order?
> Sort the list. Once sorted, we only need to compare each number with its
> neighbour and keep the smallest gap.

Apply this same chain to code, algorithms, science, history, business, anything.

## Ask yourself natural questions

Write the explanation as a conversation with your own curiosity. Sprinkle in
human questions wherever the reader would naturally wonder something:

- "So what did we use before this?"
- "Okay, so what was wrong with that?"
- "Wait, why does that happen?"
- "What's the real root cause here?"
- "So how can we fix it?"
- "Does this fix actually solve every problem we listed?"
- "Is there a catch?"

Then answer each one. Questions should feel like a real person thinking, not a
quiz.

## Always lean on the "why"

For every fact, ask "why?" until you hit something the beginner already
understands. "What" and "how" are the easy parts. The "why" is what makes it
stick. If a step has no "why", add one.

## Tone and language

- Talk to an absolute beginner. Short sentences. Everyday words.
- Explain every bit of jargon the first time it appears, in plain words.
- Use fun, concrete analogies (kitchens, shops, school, games, friends,
  everyday objects) and tie the analogy back to the real thing.
- Be warm and a little playful, never condescending.
- Use headings or bold questions so the reader can follow the journey.

## Don'ts

- Don't open with the definition of the concept. It comes after the problem.
- Don't skip the root-cause step or the "so how can we solve this?" question.
- Don't list facts without connecting them.
- Don't use jargon to explain jargon.
- Don't answer the examples in this skill. They only show the style. Answer the
  user's actual question.

## Mini skeleton

```
## Before <concept>: how did we do it?
## So what went wrong?
   Problem 1 ... Problem 2 ... (with a fun analogy)
## What's the real root cause?
   "So the root cause is ..."
## So how can we solve this problem?
## Enter <concept>
   How it fixes the root cause, step by step (each step builds on the last)
## Putting it all together
   problem → root cause → fix → why it works (+ when not to use it)
```
