# While you were away — the digest

When the desktop window regains focus after you've been away (5 minutes or
more), Twico shows a digest at the bottom of the [Home tab](home.md). It's
a one-paragraph summary of what happened — written as if a colleague were
telling you what landed in your inbox — plus a per-conversation breakdown.

The digest is **inline, gray, and subtle** by design. It's information,
not a popup. It doesn't demand action.

## How it's built

1. Twico pulls every observed inbound Slack message + every outgoing reply
   activity since you were last focused.
2. Both sides are interleaved chronologically per channel into a real chat
   transcript: `Sarah (10:34): can you check the API doc?` …
   `twico (10:35): yeah, link me the version?`
3. A single LLM call (Claude Haiku by default) receives those transcripts
   and writes:
   * An **overview** — one or two sentences capturing the feel of the
     window ("Busy hour…" / "Quiet morning…").
   * A **per-conversation summary** — 1–2 sentences per channel, with a
     `needs_followup: true` flag when the contact is still waiting on you.
4. The dashboard renders those, with follow-up channels highlighted in
   amber.

## Fallback

If no LLM key is configured (or the call fails), the digest falls back to
a deterministic one-line counts summary:

> While you were away (2.4h): answered 12 messages, 1 thread needs your
> follow-up — busiest in #engineering.

…and the per-conversation block stays hidden.

## When does it not show?

* On first launch (no recorded focus marker yet — there's nothing to be
  "back from").
* When the gap was less than ~60 seconds.
* When literally nothing happened in the window.
