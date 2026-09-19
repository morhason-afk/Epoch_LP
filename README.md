# EPOCH v3 funnel foundation

Static Netlify-ready prototype with 70/30 sticky arm allocation plus sticky 50/50 $14.99/$19.99 price-cell assignment within the paywall arm, with crossed-out anchors ($19.99->$14.99 and $24.99->$19.99), quiz, deferred-payment founding-member capture, free arm, confirmation page, three-episode placeholder player, event taxonomy, and UTM persistence.

## Deploy
Upload the directory to the existing Netlify site or connect its repository. Replace `placeholder.mp4` with approved creative. Add Microsoft Clarity in the site `<head>` only after a Clarity project ID exists.

## Events
`session_start`, `arm_assigned`, `price_cell_assigned`, `funnel_view`, `quiz_complete`, `price_selected`, `founding_email_submit`, `founding_email_success/error`, `episode_start`, `episode_progress` (25/50/75/100), `episode_replay`, `next_episode_start`, `series_complete`, `session_end`.

Events go to `dataLayer`, Microsoft Clarity when loaded, web2wave `window.w2w.logEvent` when available, and console. Session end also attempts a Netlify Function beacon placeholder.

## UTM standard
Organic: `utm_source=tiktok&utm_medium=organic&utm_campaign=epoch_organic_[YYYYMM]&utm_content=[archetype]_[hook]_[variant]`
Paid/Spark: `utm_source=tiktok&utm_medium=paid_social&utm_campaign=epoch_test1_[YYYYMM]&utm_content=[archetype]_[hook]_[variant]&utm_term=[audience]&utm_id=[campaign_id]`
Preserve `ttclid`. Never use hash fragments before query parameters.


## TikTok Pixel
Pixel `DAN591JC77U5PB5VV4I0` is loaded in the document head with the standard `ttq` loader and `ttq.page()`. Mapping: landing/quiz/player view -> `ViewContent`; quiz complete -> `ClickButton`; paywall exposure -> `InitiateCheckout` plus custom `PriceCellView`; founding email submit -> `SubmitForm` plus custom `Lead`; episode start/progress/next/replay/series complete -> same-named custom events. Every event carries arm, exact price_cell, stored UTM fields, ttclid, session and episode.
