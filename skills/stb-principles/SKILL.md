---
name: stb-principles
description: Applies Sean Barrett's stb library principles to any code or system, in any language - easy to use first, few dependencies, one idea per module, small public interface, small footprint, honest limits, explicit context, plain code. Use when writing, reviewing, refactoring or designing code, modules, APIs or services, or when the user says "stb", "stb-style" or "Barrett rules".
---

# STB principles

Eight rules from Sean T. Barrett's stb libraries, made general. Rule 1 decides ties between the others.

Sources: [stb_image.h "Philosophy"](https://github.com/nothings/stb/blob/master/stb_image.h), [docs/stb_howto.txt](https://github.com/nothings/stb/blob/master/docs/stb_howto.txt), [README FAQ](https://github.com/nothings/stb).

## 1. Easy to use, then easy to maintain, then fast

Barrett: "1. easy to use 2. easy to maintain 3. good performance."

- Pick the version a caller can use without mistakes from its signature alone.
- Pick readable over clever. Optimize only with a measurement in hand.
- When two options tie, take the one with fewer ways to misuse it.
- **Systems:** the default path through a service or tool is the correct one. No setup step the caller can forget.

## 2. Few dependencies

Barrett: "Don't rely on anything other than the C standard libraries."

- Reach for the language's standard library or platform first.
- Add no package for something a few lines can do.
- Need one anyway? Pin it, say why, and wrap it in one module so nothing else imports it.
- Use what the codebase already uses before you bring in a second tool for the same job.
- **Systems:** each outside service is one more thing that can go down. Put each behind one seam you can swap.

## 3. One idea, one self-contained module

Barrett: "the difference between 2 files and 1 file is a big deal."

- One idea lives in one module you can read top to bottom.
- Don't split a small idea across many tiny files. Don't pile unrelated ideas into one large file.
- Touch the fewest files the change needs.
- **Systems:** one job per service. Don't split one job across services that must deploy together.

## 4. Small public interface, private internals

Barrett puts public names under one prefix and private ones under another, so internals never leak.

- Expose only what another module uses. Keep the rest private with the language's own tools.
- No exports kept for tests when the test can go through the public path.
- Before adding one, search for an existing one that does the job.
- **Systems:** few endpoints, few config options, few flags. Each one is a promise you keep forever.

## 5. Small footprint, narrow scope

Barrett stopped adding formats because each one "increases the amount of code we need to secure."

- Change only what the task needs. No side refactors in the same change.
- Each new line is code someone secures and maintains. Delete before you add.
- Say no to options nobody asked for.
- **Systems:** each feature, port and permission adds attack surface. Ship the smallest set that does the job.

## 6. Usage notes and honest limits up front

Each stb header opens with how to use it, its options, and what it does not guarantee.

- Start any non-obvious module with one short note: what it does, how to call it, what it does not promise.
- State limits in plain words: "Safe against crashes. Not safe against power loss."
- Update a comment in the same change that makes it wrong. A false comment is worse than none.
- Match the comment density around you.
- **Systems:** the README or service doc says what fails, what isn't atomic, and which limits exist.

## 7. Pass context in, no hidden global state

Barrett: "consider letting the user pass in a context ... Otherwise, users may have to use global or thread-local variables."

- Pass dependencies in as arguments.
- No module-level mutable state, global registries or singletons.
- No side effects that run because something got imported or loaded.
- **Systems:** no shared mutable config that changes behavior at runtime without the caller knowing. Pass it in the request or at startup.

## 8. Plain, direct code

Barrett: the library should be "easy to invoke (which requires good API design)."

- Plain functions over classes, factories, or interfaces with one implementation.
- Straight-line code a tired reader gets on the first pass.
- Name things for what they do.
- Fail with one clear error, close to the cause. Never swallow an error into an empty value.
- **Systems:** one clear error at the boundary beats silent retries and fallbacks that hide the cause.

## Checklist before you call a change done

1. Can a caller use it without mistakes from the signature or docs alone?
2. Zero new dependencies, or one that's pinned, justified and wrapped?
3. Fewest files or services, each holding one idea?
4. Is each new public name or endpoint used somewhere?
5. Does the diff touch only what the task needs?
6. Do non-obvious parts state what they don't guarantee, and is each comment you touched still true?
7. No new global state, singletons or load-time side effects?
8. No class or layer where one function works, and no swallowed errors?
