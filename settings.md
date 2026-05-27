# Settings

Avatar menu → **Settings**. Four sections, all configurable in place.

## 1. Agent engine

* **opencode** (recommended) — runs the full opencode agent loop with
  real file tools (read/grep/edit your knowledge folders) plus Twico's
  own tools. Twico's installer bundles a matching opencode binary on
  macOS/Windows; on Linux + dev runs, install via
  `npm i -g opencode-ai` or `curl -fsSL https://opencode.ai/install | bash`.
* **Built-in** — lightweight single-pass agent. Fewer tools, no extra
  install. Falls back here automatically if opencode isn't found.

The status line confirms which is detected.

## 2. LLM provider

* **OpenRouter** (hosted) — drop in your `sk-or-v1-…` key and pick a
  preset model (Claude Haiku 4.5 / Sonnet 4.6 / GPT-4o mini) or type a
  `provider/model-id` custom slug.
* **Ollama** (local) — set the URL (defaults to `http://localhost:11434`)
  and click **Save &amp; detect**. Twico probes `/api/tags` and lists the
  models installed on your machine. Pick one and **Use this model**.

> Opencode currently only routes through OpenRouter — if you choose the
> Ollama provider, Twico falls back to the built-in engine automatically.

## 3. Slack

Click **Detect Slack workspaces**. Twico reads the session your Slack
desktop is signed into (xoxc token + the `d` cookie), shows you every
workspace it finds, and connects the one you pick. Credentials are written
to your OS keyring (Keychain on macOS, Credential Manager on Windows,
libsecret on Linux), never to the SQLite database.

Each connected account has **Pause** and **Disconnect** controls.

## 4. Agent skills (advanced)

Add custom MCP servers the agent can call. Each skill is `name` +
`command` (e.g. `crm` + `/usr/local/bin/crm-mcp --stdio`). Opencode also
auto-discovers native skills you drop into
`~/.config/opencode/skills/<name>/SKILL.md`.
