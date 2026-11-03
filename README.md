# VALLIS Liquidity — Traffic Hub (GareBear Hub)

A lightweight traffic hub for the VALLIS ecosystem + ADMENSION.

What it does
- Captures UTM/referrer/adm params and routes users to the right
  subsystem: ADMENSION by default, VALLIS / wiki / games on request
- Logs a `hub_hit` and `hub_redirect` to the ADMENSION collector
  (optional — only if a collector URL is set)
- Preserves params on redirect so ADMENSION can attribute
  contributions correctly
- `/r/<code>` resolves ADMENSION short links through the collector

How to publish (5 min) — corrected 2026-11-03
1) Enable GitHub Pages on **this** repo (Settings → Pages → Deploy
   from a branch → `main`, `/ (root)`). The hub goes live at
   https://garebear99.github.io/VALLIS_Liquidity/
2) No `garebear99.github.io` root repo is needed **for this router**:
   every link in this hub is an absolute
   `https://garebear99.github.io/ADMENSION/...` URL, so the router
   works from its own project URL. (The old README told you to create
   the root repo and use `../ADMENSION/` relative links — those only
   worked from a root site that never existed. Fixed 2026-11-03.)
   NOTE (2026-11-03): a root repo IS still needed for **AdSense** —
   the `garebear99.github.io` site needs `ads.txt` and the AdSense
   code at the domain root before it can be approved. That is a
   separate ready-to-push package (`root-site/` in the work folder),
   not a requirement of this router.
3) (Optional, for hub logging) Set your collector URL by editing
   `index.html` and adding:
   ```html
   <script>window.ADMENSION_COLLECTOR_URL='https://script.google.com/macros/s/.../exec'</script>
   ```
4) (Required, for `/r/<code>` short-link resolution) Set the same
   collector URL in `r/index.html`. Without it the resolver shows
   "Link resolution is not configured yet" instead of erroring.

Usage tips
- To force immediate redirect without the hub UI, append `?auto=1`.
- To route to VALLIS explicitly: `?to=vallis`.
- ADMENSION params like `adm`, `utm_*`, `s`, and `seed` are preserved across the redirect.

Status (2026-11-03): the hub routes correctly, but VALLIS pools are
not live and the games are docs previews — no live funds, no deposits,
no payouts made yet.
