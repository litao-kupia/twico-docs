# History tab

Every message your twin has handled — answered, skipped, muted, or flagged
for follow-up — lands here.

## Summary cards

Four cards across the top: This session, Last hour, Last day, Last week.
Each shows the total count plus a breakdown of sent / skipped / errors /
follow-ups.

## Filter strip

Above the list:

* **Search** — free-text match against reply text, error messages, and
  channel labels. Case-insensitive substring, debounced 120ms.
* **All channels** — narrow to one channel (auto-populated from your data).
* **All kinds** — `sent` (the twin answered), `skipped` (deliberately not
  answered), `needs_followup` (afk reply sent — see
  [Follow-ups](follow-ups.md)), `muted` (the channel was told to stop —
  see [Muting](muting.md)), `error` (something went wrong).
* **All time** — last hour, day, week, 30 days, or all.

Filters combine — pick more than one to narrow further.

## Rows

Each row shows:

* A **timestamp** (your local time).
* The **channel label**.
* The **kind badge** on the right (color-coded).
* A **preview** of the reply or error, truncated at 160 characters.

Click any row to expand it inline and read the full content. The
yellow-bordered rows are open follow-ups. Muted rows fade slightly.

## Pagination

20 rows per page, **Prev / Next** at the bottom. The list re-fetches
automatically when new activity lands.
