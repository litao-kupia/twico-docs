# Getting started

## 1. Install Twico

Download the installer for your OS from [twico.io](https://twico.io). On Linux,
either install the `.deb` (`sudo dpkg -i Twico_X.Y.Z_amd64.deb`) or run the
bare binary. macOS and Windows installers are signed for the auto-updater but
not for the platform stores yet — macOS will ask you to confirm the first run
(right-click → Open).

## 2. Sign in

The first screen pairs the desktop app to your Twico account.

1. Click **Open sign-in page in browser**.
2. Sign in (or sign up) at twico.io.
3. The page shows a 6-character pairing code. Paste it into the desktop app
   and press **Continue**.

If the browser doesn't open automatically, click the URL pill — it copies the
link to your clipboard and opens it in your default browser.

## 3. Pick a language model

Open **Settings** from the avatar menu in the top-right.

* **Agent engine**: pick **opencode** (recommended) if you have it installed.
  Otherwise the built-in engine works too — it just has fewer tools.
* **LLM provider**: **OpenRouter** is the easiest — pay-per-token, dozens of
  models. Drop in your `sk-or-v1-…` key and pick a model from the list.
  **Ollama** lets you run a local model on your machine for free; click
  **Save & detect** and Twico will list your installed models.
* **Model**: Claude Haiku 4.5 is the default — fast and cheap. Sonnet is
  smarter; GPT-4o mini works too.

## 4. Connect Slack

Still on the Settings page, scroll to **Slack** and click **Detect Slack
workspaces**. Twico reads the session your Slack desktop client is already
signed into — your credentials never leave your machine.

Pick a workspace; it gets connected as you.

## 5. Watch the first reply land

Go to the **Home** tab. The pause orb is green ("Twico is on"), and the
**Today** line will start filling in as messages arrive. Click into **History**
for a full transcript.

If anything's confusing on the first run, see [Troubleshooting](troubleshooting.md).
