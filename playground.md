# Playground — test replies safely

The **Playground** (avatar menu → Playground) lets you ask the twin "how
would you reply to this?" without anything going to Slack.

It uses your real Persona, Knowledge, and Memory — so the answer is what
the twin *would* say if this message landed for real. It also uses the
configured opencode tools (web search, knowledge search, etc.).

## How to use it

1. Type a message into the input box as if someone sent it to you.
2. Press **Send** or **Cmd/Ctrl+Enter**.
3. The twin's reply appears in the chat pane, with a note explaining the
   reasoning if useful.

## Reset

The small ↻ icon at the top-right of the page clears the conversation.
Useful between different test scenarios; the twin maintains short-term
context across messages in the same playground session.

## Watch the trace

While a playground reply is being computed, open **Live trace** (avatar
menu) in another tab to see every tool call the agent makes in real time.
This is the cleanest way to understand *why* the twin replied the way it did.
