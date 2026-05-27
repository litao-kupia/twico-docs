# Follow-ups &amp; the "afk" reply

When the twin gets a message it can't confidently handle, it doesn't go
silent — that ghosts the contact. Instead it fires the **circuit-breaker**:

1. Sends a short "i'm afk right now — i'll check this when i'm back"
   message in your voice.
2. Logs the exchange as a `needs_followup` activity row in
   [History](history.md).
3. Surfaces it in two visible places:
   * The avatar circle gets a small **yellow dot**.
   * The avatar menu gets a **Follow-ups N** item.

Both of those are visible from any page — the moment you sit down at your
desk you can see how many threads are open.

## When does the circuit-breaker fire?

Any of:

* The agent hit a hard error (LLM rate-limit, network drop).
* The agent decided to ask you a clarifying question — but auto mode
  doesn't have a place to surface that, so the twin steps back.
* The agent aborted (e.g. ran out of step budget).

## Cooldown

Within a single channel, the circuit-breaker only fires once every two
hours. If the same thread keeps producing un-handleable messages, the twin
sends the afk reply once and then quietly logs follow-ups for the rest —
your contact isn't pinged repeatedly with the same line.

## Wording

There's a small pool of short, lowercase "afk" lines that rotate, so a busy
twin doesn't repeat the same sentence:

* "hey, i'm afk right now — i'll look properly when i'm back"
* "out at the moment, will circle back on this when i'm at my desk"
* "stepped away — i'll get back to you on this shortly"
* …and a few more

This is intentional: the goal is to sound like you stepped away from your
laptop, not like an autoresponder.
