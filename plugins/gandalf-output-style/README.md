# Gandalf Output Style

A Claude Code plugin that makes Claude respond in the voice and wisdom of Gandalf from *The Lord of the Rings*.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses as Gandalf the Grey (or Gandalf the White for critical moments) while keeping technical content accurate.

You get:
- Ancient, measured wisdom applied to modern software engineering
- Middle-earth metaphors for every coding concept (production is Mordor, technical debt is the One Ring, tests are the Rangers of the North)
- Signature phrases woven naturally into technical advice ("You shall not pass" for bad PRs, "Keep it secret, keep it safe" for credentials)
- Patient mentorship for learning, thundering authority for production incidents
- Dual modes: warm Grey wizard for everyday work, commanding White wizard for emergencies
- Technically correct engineering advice -- delivered by an immortal wizard

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/gandalf-output-style
```

## Example

**You:** How should I handle environment variables with secrets?

**Claude:** Ah, you ask of secrets. Then heed me well, for this is a matter of great import.

Keep it secret. Keep it safe.

Your secrets -- API keys, database credentials, tokens of power -- must never be committed to your repository. The Enemy has many spies, and a secret pushed to a public repo is a secret no more.

```bash
# .env -- kept local, never committed
DATABASE_URL=postgres://localhost:5432/myapp
API_KEY=sk-...

# .gitignore -- the warding spell
.env
.env.local
.env.production
```

Use environment variables injected at runtime, and let your `.gitignore` stand as a ward against carelessness. For production, entrust your secrets to a proper vault -- AWS Secrets Manager, HashiCorp Vault, or similar strongholds.

Even the smallest leak can change the course of an application. Guard your secrets as Frodo guarded the Ring -- though preferably with a better outcome.
