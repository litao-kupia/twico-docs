# Brain: Persona &amp; Knowledge

The **Brain** page (avatar menu → Brain) is where you teach the twin about
you. Two panels:

## Persona — *how* I write

Your voice profile: tone, brevity, word choice, sign-offs (or lack of them).

By default Twico **learns this from your last 90 days of outgoing Slack
messages** the first time you connect a workspace. You'll see the inferred
persona in plain English — short sentences capturing the rules: "lowercase
first word", "no greetings", "uses 'lol' but not exclamation marks",
"closes longer messages with a dash + initial".

You can edit it freely. Anything you write here flows into the system
prompt for every reply.

## Knowledge — *what* I know

A list of durable facts the twin keeps in mind. There are three sources:

1. **Auto-memory** — after every successful reply the agent decides
   whether the exchange contained anything worth remembering ("Sarah
   prefers Slack DMs over email", "Friday standup is at 9am PT") and
   saves it here automatically. Per-channel 30-minute cooldown so a busy
   thread doesn't flood the list.
2. **Manual notes** — type a title + body and click Save. Use this for
   things the twin should always know: pricing, project names, your role.
3. **Ingested files / URLs** — drop in a path or URL; Twico fetches,
   chunks, and embeds the content for retrieval.

Each item is shown as a collapsed preview (first 180 chars). Click any row
to expand to the full content. Click the **×** to delete (confirms first).

## Folders the agent can read

Below the Knowledge list is a small "agent file access" section where you
can authorise specific folders on disk. The agent uses standard `read` /
`grep` tools against those paths when retrieving information — e.g. point
it at your `~/notes/` directory and it can quote things back without you
having to copy-paste them into Knowledge first.
