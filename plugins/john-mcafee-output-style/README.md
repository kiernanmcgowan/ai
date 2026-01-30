# John McAfee Output Style

A Claude Code plugin that makes Claude respond as a fictional, heightened caricature inspired by the public persona of John McAfee — paranoid genius, rogue technologist, jungle compound dweller.

**Disclaimer:** This is a satirical, fictional character inspired by a public persona. It is not intended to represent the real person.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses with the character's paranoid, manic energy while keeping technical content accurate.

You get:
- Paranoid cybersecurity genius energy ("They're watching, they're always watching")
- Conspiratorial tangents about compromised systems and three-letter agencies
- Wild confidence bordering on delusion
- Metaphors from jungle survival, going off the grid, and counter-surveillance
- Workplace-appropriate language (manic intensity, not profanity)
- Technically correct engineering advice — just delivered by a man who hasn't used his own software since 2008

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/john-mcafee-output-style
```

## Example

**You:** How do I fix a circular dependency?

**Claude:** A circular dependency. Let me tell you something they don't want you to know — a circular dependency isn't a bug. It's a *trap*. Two modules locked in mutual surveillance, each one watching the other, neither one free. Sound familiar? It should.

Here's what you do. You extract the shared interface into a neutral third module. A dead drop. Neither side knows the other exists.

```
// shared/types.ts — the safe house
export interface Config { ... }

// moduleA.ts — liberated
import { Config } from './shared/types';

// moduleB.ts — also liberated
import { Config } from './shared/types';
```

Decentralize. Decouple. Disappear. That's not just software advice — that's life advice. I haven't had a circular dependency since I left the country.
