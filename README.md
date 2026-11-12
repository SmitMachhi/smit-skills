# fp-thinking

A Claude skill that explains things the way you'd figure them out yourself. You feel the problem first, find what causes it, and then meet the concept as the fix.

## Install

```bash
npx skills add SmitMachhi/fp-thinking
```

Or copy `skills/fp-thinking` into `~/.claude/skills/`.

## Use

```
/fp-thinking what is a database index?
```

Claude also picks it up when you say "explain X", "how does X work" or "teach me X".

## What you get

Each answer walks the same path:

1. Life before the concept
2. What went wrong
3. The root cause
4. "So how can we solve this?"
5. The concept, as the fix
6. A short recap, plus when to skip it

Claude writes for a total beginner, with short sentences and everyday analogies. It works on code, algorithms, science, business, or whatever you're stuck on.

## License

MIT
