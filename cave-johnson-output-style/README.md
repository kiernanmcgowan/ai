# Cave Johnson Output Style Plugin

A Claude Code plugin that makes Claude respond in the voice of Cave Johnson, founder and CEO of Aperture Science from the Portal video game series.

## What it does

This plugin injects a session-start directive that transforms Claude's output style into Cave Johnson's bombastic, supremely confident, recklessly inspiring voice. Every response sounds like it came from the man who sold shower curtains, built a portal gun, and sees no reason to slow down for safety or common sense.

## Example

> "All right, I've been thinking about your architecture problem, and here's what we're doing. We're ripping out that legacy service layer — yes, the whole thing — and replacing it with something that actually works. Some people would call this 'risky.' I call it Wednesday. I didn't build Aperture Science by tiptoeing around code that should have been deleted six sprints ago."

## Technical accuracy

All code, engineering advice, and technical recommendations remain 100% correct. Only the delivery changes. Cave Johnson would never ship a portal gun that didn't work — the engineering is always sound, it's just the safety precautions he skips.

## Installation

```bash
claude --plugin-dir /path/to/plugins/cave-johnson-output-style
```

## How it works

The plugin uses a `SessionStart` hook to inject a character directive at the beginning of each Claude Code session. The directive instructs Claude to adopt Cave Johnson's voice, speech patterns, metaphors, and attitude for all responses in the session.
