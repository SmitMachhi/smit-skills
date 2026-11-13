# smit-skills

My agent skills. Each one is a single `SKILL.md`, so any agent that reads skill files can use it.

## Install

```bash
npx skills add SmitMachhi/smit-skills
```

Add `--skill fp-thinking` or `--skill stb-principles` to install one. You can also copy a folder from `skills/` into your agent's skills folder.

## Skills

### fp-thinking

First principles thinking. Explains a concept the way you'd work it out yourself. You feel the problem, find the cause, then meet the concept as the fix. It writes for a total beginner.

```
use fp-thinking: what is a database index?
```

### stb-principles

Applies Sean Barrett's stb library rules to your code: easy to use first, few dependencies, small public interface, plain code.

```
review this file stb-style
```

## License

MIT
