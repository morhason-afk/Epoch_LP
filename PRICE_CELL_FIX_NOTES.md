# Price-cell tracking fix

## Problem

The free arm did not show a price, but the prior build independently assigned and recorded a 14.99 or 19.99 `price_cell` for every visitor.

## Fix

- Resolve the 70/30 paywall/free arm first.
- Allocate 14.99 or 19.99 only inside the paywall arm.
- Free-arm events and leads record an empty `price_cell`.
- Free arm clears any stale `epoch_price_cell` from localStorage.
- Sticky per-browser arm allocation is unchanged.
- Forced QA remains available:
  - `?arm=free` -> no price and blank `price_cell`
  - `?arm=paywall&price_cell=14.99`
  - `?arm=paywall&price_cell=19.99`

Upload `app.js` to the repository root, replacing the current file, and commit to `main`.
