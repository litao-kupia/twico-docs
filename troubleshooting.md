# Troubleshooting

## Slack doesn't show up under "Detect Slack workspaces"

* Make sure Slack desktop is installed **and signed in** to at least one
  workspace. Twico reads its leveldb cache; an un-signed-in desktop has
  nothing to extract.
* On Linux the extractor wants `libsecret`. On Ubuntu/Debian:
  `sudo apt-get install libsecret-1-0`.
* Snap/Flatpak versions of Slack ship to non-standard data dirs — Twico
  probes the common ones automatically; if yours isn't found, the .deb
  Slack from `slack.com/downloads/linux` is the most reliable.

## "OpenRouter not configured"

Settings → LLM provider → drop in your `sk-or-v1-…` key. Get one at
[openrouter.ai/keys](https://openrouter.ai/keys). The free credit on a
new account is more than enough to test the twin for a day.

## "Couldn't reach Ollama at …"

Ollama runs as a local HTTP server. Start it with `ollama serve`, then
click **Save &amp; detect** in Settings. Pull at least one model first
(`ollama pull llama3.2`).

## The twin replied something I don't like

Three layers to adjust:

1. **Persona** (Brain → Persona) — edit the voice rules directly. The
   change applies to every future reply.
2. **Knowledge** (Brain → Knowledge) — add facts the twin should know
   about you. Auto-memory will keep adding more as it sees patterns.
3. **Live trace** (avatar menu) — see exactly which tools the agent
   called and what it received back. Useful for "wait, why did it say
   that?".

## I want to undo an auto-reply

You can't unsend a Slack message from Twico itself — but the message you
sent appears in your normal Slack history, edit/delete with `Cmd+Up` /
the message hover menu.

To prevent future replies in that channel, open **Channels** (avatar
menu) and set its policy to **off**.

## I told the twin to stop and it's still replying

It probably didn't recognise the stop signal. Patterns that always work:

* `@<your_name> stop`
* `@<your_name> shut up`
* "We don't need your assistant in this thread"

If a different phrasing isn't catching, mention the twin's account in the
channel + then say stop. Both signals together always trigger.

## App started in Paused state again

That's intentional — Twico **resets to Paused on every sign-out and quit**
so it doesn't start auto-answering before you've reviewed. Click the orb
on the Home tab to resume.
