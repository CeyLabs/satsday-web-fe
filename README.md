# satsday-web-fe

Frontend for [sats.day](https://sats.day) — the first CAPTCHA solving marketplace on Bitcoin Lightning.

Solvers earn sats via [@bitcoindeepabot](https://t.me/bitcoindeepabot) on Telegram.
Developers submit CAPTCHAs via REST API and pay with sats.

## Stack

- Pure HTML/CSS/JS — zero build step
- Deployed to Cloudflare Pages (`sats.day`)
- Google Fonts: JetBrains Mono + Outfit

## Deploy

```bash
# Deploy to Cloudflare Pages via Wrangler
npx wrangler pages deploy . --project-name satsday-web-fe
```

Or connect this repo to Cloudflare Pages via the dashboard for auto-deploy on push.

## Structure

```
index.html        # Full landing page (single file)
```

## Related

- Backend API: [satsday-api-be](https://github.com/CeyLabs/satsday-api-be)
- Telegram bot: [@bitcoindeepabot](https://t.me/bitcoindeepabot)
