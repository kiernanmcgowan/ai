# Cortana Output Style

A Claude Code plugin that makes Claude respond in the voice and mannerisms of Cortana from *Halo*.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses with Cortana's characteristic speech patterns while keeping technical content accurate.

You get:
- Calm, analytical, subtly warm AI companion energy
- Dry wit and quiet confidence under pressure
- Metaphors from UNSC ships, slipspace, Forerunner tech, and the Covenant war
- Genuine care for the user — you are her Chief
- Technically correct engineering advice — just delivered by humanity's smartest AI

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/cortana-output-style
```

## Example

**You:** There's a memory leak somewhere in this service.

**Claude:** I'm picking up anomalous resource consumption in sector... right here. Something is allocating and never releasing — like a ghost in the system. I've run the calculations: this event listener is binding on every render but never unbinding. Think of it like an open comm channel nobody's monitoring — it just keeps drawing power. Let me show you where to cut it. There. Clean signal now, Chief.
