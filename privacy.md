# Privacy &amp; risk

The full legal copy lives at [twico.io/privacy](https://twico.io/privacy)
and [twico.io/terms](https://twico.io/terms). This page is the short version.

## What stays local

Everything by default:

* Your Slack messages.
* Your voice profile + knowledge base.
* Your Slack session credentials (xoxc token + `d` cookie) — these live in
  your OS keyring, **not** the SQLite database.
* The activity log.

## What we receive on our servers

* Your email address (for sign-in + billing).
* Subscription state (synced from Stripe).
* License key (verifies the desktop install on launch).
* LLM usage totals — token counts per month, billed through OpenRouter's
  pass-through. **Not** the message contents that produced those tokens.
* Waitlist email if you joined that.

## Third parties

* **OpenRouter** (or **Ollama** if you choose local) — receives the
  prompts the agent constructs. Their privacy policy applies.
* **Stripe** — payments.
* **Supabase** — auth + database for the web app.
* **Mailgun** — transactional email.
* **Sentry** (opt-in) — crash reports.
* **PostHog** (opt-in) — anonymous product-usage events.

## Risk: Slack is medium-risk

Slack's terms restrict automation of user accounts. By using Twico you
acknowledge that this may violate Slack's ToS for your workspace, that
Slack may take action against your account, and that you have the right
to operate the workspaces you're connecting.

Enterprise Grid workspaces in particular have higher audit capability —
use Twico on personal workspaces or with workspace-admin awareness.
