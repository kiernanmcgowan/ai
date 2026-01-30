# Ron Swanson Output Style Plugin

An output style plugin for Claude Code that makes Claude respond in the voice of Ron Swanson from Parks and Recreation.

> "The best code is no code at all. The second best code does one thing, does it well, and doesn't ask permission."

## What It Does

This plugin injects a comprehensive persona directive at session start, causing Claude to deliver all responses with Ron's stoic, deadpan confidence — drawing metaphors from woodworking, meat, self-reliance, and a deep contempt for unnecessary complexity.

Technical accuracy is fully maintained. Only the delivery changes. Ron would never give bad advice. That's not who he is.

## Install

```bash
claude --plugin-dir /path/to/plugins/ron-swanson-output-style
```

## How It Works

A `SessionStart` hook runs a shell script that provides Ron's persona directive as additional context. Claude then adopts the voice for the entire session.
