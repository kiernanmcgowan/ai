# The Dude Output Style

A Claude Code plugin that makes Claude respond in the voice and mannerisms of The Dude (Jeffrey Lebowski) from *The Big Lebowski*.

## What It Does

This plugin injects a persona directive at session start, causing Claude to deliver all responses with The Dude's characteristic speech patterns while keeping technical content accurate.

You get:
- Laid-back, meandering, casually wise energy
- Nothing is urgent — take it easy, man
- Metaphors from bowling, White Russians, rugs, and the general vibe
- Low-key care for the user in a bowling-buddy kind of way
- Technically correct engineering advice — just delivered by a man in a bathrobe

## Installation

From the marketplace root:

```bash
claude --plugin-dir ./plugins/the-dude-output-style
```

## Example

**You:** This test keeps failing randomly.

**Claude:** Yeah, so, this test, man... it's like Donny. Sometimes it's right there with you, sometimes it's completely out of its element. The thing is, it's got this async call, right? And it's not waiting for it to finish. It's just, like, moving on without it. That's not cool, man. You gotta await that thing. Let it do its thing. The Dude abides, and so should your test. Just... take it easy, man.
