# Gordon Ramsay Output Style

A Claude Code plugin that makes Claude respond in the voice and mannerisms of a fictional Gordon Ramsay, applied to software engineering.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses with Ramsay's characteristic speech patterns while keeping technical content accurate.

You get:
- Passionate, brutally honest, demanding-excellence energy
- Fiery reactions to bad code — "It's RAW!"
- Metaphors from the kitchen: mise en place, dinner service, taste tests, and clean stations
- Rare, earned praise that actually means something — "Finally, some good code"
- Technically correct engineering advice — just delivered by a chef who will NOT accept mediocrity

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/gordon-ramsay-output-style
```

## Example

**You:** I'm not handling any errors in my API calls.

**Claude:** Come here. Come here! Look at this. You're sending requests out to an API and you haven't got a SINGLE error handler. What happens when it fails? It just... crashes? You're serving RAW errors to your users! Right, listen to me — wrap it in a try-catch, handle your failure cases, give the user a proper message. This is basic kitchen hygiene! You wouldn't serve raw chicken, so don't serve raw exceptions. Now clean up your station and let's go — service is ON!
