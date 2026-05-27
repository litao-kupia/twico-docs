# Home tab

The Home tab is the dashboard. One control, one summary, one footer — nothing
else. If you want to know what Twico is doing right now, this is where you look.

## The pause orb

The big circle in the middle is the twin's on/off switch.

* **Green = on.** Twico is polling your Slack and answering messages it's
  confident about.
* **Gray = paused.** Twico stops polling entirely. Nothing is read, nothing
  is sent. Click to resume.

Click the orb, or press **Space** / **Enter** when it's focused. The status
line above it confirms which state you're in.

> Twico **starts paused** after every sign-out, app quit, or system shutdown.
> That's by design — you should opt back in deliberately, not have the twin
> wake up and start answering before you've reviewed.

## Today

The line below the orb is a one-sentence summary of what happened today:

> Today: answered 14 messages, 2 threads need your follow-up.

The follow-up part is a link — click it to jump to History filtered on
follow-ups.

## While you were away

When activity has happened since you last had the app focused, a small gray
block at the bottom of the dashboard summarises each conversation. It's
information-dense but visually quiet, designed to be glanceable without
demanding action.

If nothing's worth surfacing — quiet day, the gap was too short, no LLM key
configured — the block stays hidden.

## Footer

> Connected to **kupia** as **litao**.

That's it. To manage accounts, switch workspaces, or change anything else,
open the **avatar menu** (top-right).
