---
name: constraint-first-debugging
description: Verify platform/API constraints before writing code. Bottom-up debugging from uncontrollable layers.
triggers:
  - Trying to implement a feature but unsure if it's possible
  - Involving third-party API / platform limitations
  - Feeling like you're going in circles during debugging
  - User asks "can we do X?"
---

# Constraint-First Debugging

## Core Principle

**Verify what you can't control before investing in what you can.**

Many "bugs" are actually platform limitations disguised as code problems. Fixing the wrong layer wastes hours.

## Debugging Layers (Bottom-Up)

1. **Platform/API layer** (uncontrollable) — official docs, API reference, known limitations
2. **Protocol/Format layer** (semi-controllable) — data formats, encoding, transport
3. **Code/Logic layer** (controllable) — everything we can change

## Steps

1. **Define the goal** — what exact behavior do we want?
2. **Read the docs** — does the platform API explicitly support this?
3. **Find evidence** — search GitHub issues, forums, Stack Overflow for successful implementations
4. **Quick validation** — test with a minimal API call (curl / one-liner)
5. **If API doesn't support it → STOP** — don't try to work around it with client code
6. **If API supports it → debug the code layer**

## Checklist

Before writing any code:

- [ ] Does official documentation confirm this feature is supported?
- [ ] Has anyone else successfully implemented this? (GitHub issues / forums)
- [ ] Did you run the simplest possible API test?
- [ ] If unsupported, is there an alternative that achieves 80% of the goal?

## Anti-Pattern: WeChat Voice Bubble (2026.05.26)

**Goal**: Send native WeChat voice bubbles from a bot

**Wrong path**: Modify `send_voice()` → install pilk encoder → fix regex → fix extension handling → keep going...

**Root cause**: iLink Bot API rejects `voice_item` outbound (`ret=-2`). Server-side restriction by Tencent.

**Wasted**: 2-3 hours of code changes, all useless

**Correct approach**: First call should have been a curl test sending voice_item to the API

## When to Use

- Third-party API integration
- Platform feature development (WeChat, Telegram, Discord, etc.)
- Any "does platform support X?" judgment call
- Debugging where code changes don't seem to fix the problem
