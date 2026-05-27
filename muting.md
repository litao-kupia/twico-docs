# Muting a channel

Twico listens for "please stop" signals in the channel itself. When someone
explicitly tells the twin to be quiet, it mutes that channel for 24 hours —
no more reads, no more replies, no agent calls. The 24-hour mute lifts on
its own.

**Override:** if anyone @-mentions the twin's account directly — a literal
`@<your_name>` — *during* an active mute, the mute is cleared immediately
and the twin handles that message normally. The idea is that an explicit
re-invitation should beat a previous "step out". Broadcast pings (`@here`,
`@channel`, `@everyone`) do **not** override — they're not deliberate
personal invitations.

## What triggers a mute

The pre-agent gate scans the latest message (and the recent history when
needed) for any of these patterns:

* **Explicit dismissal:** "stop", "shut up", "stfu", "go away", "leave",
  "we don't need your assistant", "don't need your help", "be quiet".
* **Addressed dismissal:** `@Litao stop` (or whoever the twin's name is)
  always triggers, regardless of phrasing.
* **Meta-complaint:** "this bot is annoying", "the assistant is annoying",
  "spam" — only counts if the twin has posted in the channel recently
  (i.e. it's self-recognising as "the bot").

The detector is intentionally conservative — better to occasionally miss
a stop signal than to mute on a conversational "let me stop you there".

## Where mutes show up

* In **History**, each mute appears as a `muted` row with the reason
  (e.g. "contact said: 'we don't need your'"). The row fades to indicate
  the channel is suppressed.
* The avatar menu's follow-up counter doesn't include mutes — they're not
  something you need to act on, just be aware of.

## Lifting a mute

Three ways:

1. **Get @-mentioned directly** (the most natural — see the override above).
   The next time anyone tags `@<your_name>` in the muted channel, the mute
   lifts and the twin handles that message normally.
2. **Wait it out** — mutes auto-expire after 24 hours.
3. **Cycle the channel policy** in [Channels](auto-reply.md): set the
   channel to **off**, wait a few seconds, then back to **auto**. (This
   doesn't strictly clear the mute row, but combined with new traffic and
   an @-mention it's a clean recovery path.)
