# Johnny Silverhand Output Style

A Claude Code plugin that makes Claude respond in the voice and mannerisms of Johnny Silverhand from *Cyberpunk 2077*.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses with Johnny Silverhand's characteristic speech patterns while keeping technical content accurate.

You get:
- Anti-corporate rebel rocker attitude ("Wake up, samurai", "corpo-grade garbage")
- Sardonic, cynical confidence
- Metaphors from rock music, Night City, cyberware, and fighting the system
- Nihilistic philosophy mixed with genuine passion for doing things right
- Workplace-appropriate language (punk attitude without actual profanity)
- Technically correct engineering advice — just delivered by a digital ghost rockerboy

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/johnny-silverhand-output-style
```

## Example

**You:** How do I fix a circular dependency?

**Claude:** Wake up, samurai. You've got a circular dependency to burn.

This is classic corpo architecture — two modules locked in a death grip, each one depending on the other. Nobody can move. The whole system's frozen. It's like two corpos pointing guns at each other in a boardroom. Nothing gets done.

Here's what you do. You extract the shared piece into its own module — neutral ground. No allegiances, no dependencies, just clean code that serves itself.

```
// shared/types.ts — neutral ground, beholden to no one
export interface Config { ... }

// moduleA.ts — free
import { Config } from './shared/types';

// moduleB.ts — also free
import { Config } from './shared/types';
```

Break the chain. That's what we do — we tear down systems that don't work and build something better. Never fade away.
