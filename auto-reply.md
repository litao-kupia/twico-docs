# Auto-reply &amp; channel policy

Twico's core value proposition is **auto-reply**. The product premise: once
you've taught the twin your voice, you trust it to answer on your behalf.
There is no draft-and-approve middle ground.

Per channel, the policy is either:

* **Auto** — Twico answers as you.
* **Off** — Twico ignores this channel. No reads, no replies, no logging
  beyond confirming the message exists.

Manage them on the **Channels** page (avatar menu → Channels).

## How the twin decides whether to reply

Even when a channel is `auto`, Twico won't blindly post to every message.
Before the LLM runs, an **addressing gate** checks the latest message:

* **DMs** — almost always reply (the addressee is unambiguous).
* **Multi-party channels** — only reply if you're @-mentioned, the message
  continues a back-and-forth you're already part of, or there's a clear
  question in your wheelhouse. If the message @-mentions someone else,
  Twico stays out of the way.
* **Stop signals** — if anyone says "stop", "we don't need your assistant",
  "shut up", "this bot is annoying", or anything similar, Twico mutes that
  channel for 24 hours. See [Muting](muting.md).

When the gate says "skip", the message is marked as read in your Slack
client and logged to [History](history.md) as `skipped` with the reason.

## How the twin reasons

For messages that pass the gate, the agent uses a few sources:

* **Persona** — your voice + style, learned from your last 90 days of
  outgoing messages. See [Brain](brain.md).
* **Memory** — durable facts the twin has saved across past replies (and
  anything you've added manually under Brain → Knowledge).
* **Message history** — recent channel messages and observed conversations
  the twin has indexed.
* **Files on the message** — text, PDFs, screenshots, voice notes are all
  read before replying. See the rest of this section.
* **The web** — the agent can search + fetch URLs when an answer requires
  external context.

If after all that it's not confident, it fires the
[afk circuit-breaker](follow-ups.md) instead of guessing.

## Attachments

Twico reads files attached to messages, not just the caption:

* **Text / markdown / JSON / source code** — inlined directly (first ~4KB).
* **PDFs** — parsed with a pure-Rust PDF extractor.
* **Images** — described in 1–2 sentences via Claude vision.
* **Audio / video clips** — Slack's auto-transcription when available, with
  the type + length noted otherwise.

The extracted content becomes part of the prompt as
`[file: name.pdf — extracted text…]`.
