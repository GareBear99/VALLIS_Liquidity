# Root Site (VALLIS Liquidity)

This folder is a lightweight traffic hub for the VALLIS ecosystem + ADMENSION.

What it does
- Captures UTM/referrer/adm params at the root domain level
- Logs a `hub_hit` and `hub_redirect` to the same collector used by ADMENSION (optional)
- Routes users to the correct subsystem: `/ADMENSION/` by default, `/VALLIS/` if requested
- Preserves params on redirect so ADMENSION can attribute contributions correctly

How to publish (5 min)
1) Create a new GitHub repo named `garebear99/garebear99.github.io`.
2) Put the files from this folder at the repo root and push.
3) Enable Pages (it auto-deploys from `main`).
4) (Optional) Set your collector URL by editing `index.html` and adding:
   ```html
   <script>window.ADMENSION_COLLECTOR_URL='https://script.google.com/macros/s/.../exec'</script>
   ```

Usage tips
- To force immediate redirect without the hub UI, append `?auto=1`.
- To route to VALLIS explicitly: `?to=vallis`.
- ADMENSION params like `adm`, `utm_*`, `s`, and `seed` are preserved across the redirect.
