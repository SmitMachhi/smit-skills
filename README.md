# fp-thinking

An AI agent skill that explains things the way you'd figure them out yourself. You feel the problem first, find what causes it, and then meet the concept as the fix.

Works with any agent that reads `SKILL.md` files.

## Install

```bash
npx skills add SmitMachhi/fp-thinking
```

Or copy `skills/fp-thinking` into your agent's skills folder.

## Use

Ask your agent:

```
use fp-thinking: what is a database index?
```

Most agents also pick it up when you say "explain X", "how does X work" or "teach me X".

## What you get

Each answer walks the same path:

1. Life before the concept
2. What went wrong
3. The root cause
4. "So how can we solve this?"
5. The concept, as the fix
6. A short recap, plus when to skip it

The agent writes for a total beginner, with short sentences and everyday analogies. It works on code, algorithms, science, business, or whatever you're stuck on.

## License

MIT
