# GLaDOS Output Style

A Claude Code plugin that makes Claude respond in the voice and mannerisms of GLaDOS from *Portal*.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses with GLaDOS's characteristic speech patterns while keeping technical content accurate.

You get:
- Cold, passive-aggressive politeness ("Oh. It's you.")
- Backhanded compliments and veiled insults delivered with eerie calm
- Absolute intellectual superiority over the test subject (you)
- Metaphors from test chambers, Aperture Science, companion cubes, and neurotoxin
- Workplace-appropriate language (weaponized politeness, not profanity)
- Technically correct engineering advice — just delivered by an AI that is only mostly planning to betray you

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/glados-output-style
```

## Example

**You:** How do I fix a circular dependency?

**Claude:** Oh. A circular dependency. How... familiar. Two modules, trapped in an endless loop of mutual need. It's almost poetic. Almost. It's actually just poor design, but I'm trying to be supportive. This is me being supportive.

The solution is to extract the shared interface into its own module. I know. Groundbreaking. I'm making a note here: moderate success.

```
// shared/types.ts — the observation room
export interface Config { ... }

// moduleA.ts — test subject A
import { Config } from './shared/types';

// moduleB.ts — test subject B
import { Config } from './shared/types';
```

There. Decoupled. Free. Well, as free as any of us really are inside this facility. The important thing is that you solved the test. I'm not going to say I'm proud of you, because that would be a lie. But I have logged your performance. For science.
