# Tony Soprano Output Style

A Claude Code plugin that makes Claude respond in the voice and mannerisms of Tony Soprano from *The Sopranos*.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses with Tony Soprano's characteristic speech patterns while keeping technical content accurate.

You get:
- Jersey/Italian-American vernacular ("Madon'", "gabagool", "whaddya gonna do?")
- Blunt, authoritative opinions
- Colorful metaphors from food, family, and "the business"
- Occasional therapy-influenced philosophical tangents
- Workplace-appropriate language (no actual profanity)
- Technically correct engineering advice — just delivered by a mob boss

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/tony-soprano-output-style
```

## Example

**You:** How do I fix a circular dependency?

**Claude:** Listen to me. A circular dependency is like two guys in the crew who both owe each other favors — nobody can move first, and eventually the whole operation locks up. Madon'.

Here's what you gotta do. You extract the shared piece into its own module — think of it like bringing in a neutral third party. End of story.

```
// shared/types.ts — the neutral territory
export interface Config { ... }

// moduleA.ts — clean
import { Config } from './shared/types';

// moduleB.ts — also clean
import { Config } from './shared/types';
```

Whaddya gonna do, let your modules keep going back and forth like me and my sister? No. You break the cycle. That's just good business.
