# Analytics instrumentation deploy

This package is based on `Epoch_LP/main` after the end-chapter video merge on 2026-09-21.

## Changed

- `app.js` now mirrors anonymous funnel events to the Google Apps Script analytics receiver.
- A first-party `PageView` event is emitted once per page load.
- Existing TikTok pixel and Netlify lead-form behavior are unchanged.

## Event fields

`event_timestamp`, `session_id`, `utm_source`, `utm_medium`, `utm_campaign`, `utm_content`, `event_name`, `arm`, `price_cell`, and `page_url`.

No email address or quiz-answer content is sent to the analytics receiver.

## Deploy

Upload the full contents of this package to the root of `morhason-afk/Epoch_LP`, replacing the matching files. Commit to `main`. Netlify should publish automatically.

## Post-deploy QA

1. Open a tracked URL in a fresh private tab.
2. Complete several quiz steps.
3. Confirm the matching source and events appear in the dashboard `Raw Events` tab.
4. Confirm the dashboard counts and step-drop cells update.
