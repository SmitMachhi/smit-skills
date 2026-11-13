# smit-skills

My agent skills. Each one is a single `SKILL.md`, so any agent that reads skill files can use it.

## Install

```bash
npx skills add SmitMachhi/smit-skills
```

Add `--skill <name>` to install one, like `--skill quiz-me`. You can also copy a folder from `skills/` into your agent's skills folder.

## Skills

### fp-thinking

First principles thinking. Explains a concept the way you'd work it out yourself. You feel the problem, find the cause, then meet the concept as the fix. It writes for a total beginner.

```
use fp-thinking: what is a database index?
```

### quiz-me

Quizzes you on anything until it sticks: a page, a doc, code, or what you just talked about. You get one question at a time. Pick an option or answer in your own words. Miss one and it walks you to the answer, then asks again later with a new example.

It needs fp-thinking and [i-have-adhd](https://github.com/ayghri/i-have-adhd).

```
quiz me on how DNS works
```

### stb-principles

Applies Sean Barrett's stb library rules to your code: easy to use first, few dependencies, small public interface, plain code.

```
review this file stb-style
```

## License

MIT
