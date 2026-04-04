# satsday-web-fe

Frontend for [sats.day](https://sats.day) — CAPTCHA solving marketplace on Bitcoin Lightning.

## Structure

```
index.html        Landing page (marketing)
app/
  index.html      Solver app — Telegram Login + CAPTCHA queue + BTCPay deposit
```

## Stack

- Pure HTML/CSS/JS — zero build step, zero dependencies
- Deployed to Cloudflare Pages at `sats.day`
- Fonts: JetBrains Mono + Outfit (Google Fonts)
- Auth: Telegram Login Widget → session token via api.sats.day

## App features

- **Telegram Login** — one-click auth via `@bitcoindeepabot` widget
- **CAPTCHA solver** — continuous queue of tasks, 30s timer per task
- **Live balance** — real-time sats balance in nav
- **BTCPay deposit** — Lightning invoice QR for adding credits
- **Activity feed** — recent solve history with accuracy tracking
- **Withdraw** — via `/withdraw` in `@bitcoindeepabot`

## GitHub Actions (auto-deploy on push)

Add these secrets to the repo (Settings → Secrets → Actions):

| Secret                  | Value                              |
|-------------------------|------------------------------------|
| CLOUDFLARE_API_TOKEN    | CF API token with Pages:Edit       |
| CLOUDFLARE_ACCOUNT_ID   | 82c5ee4b5bf756e6658c8d9807d21592  |

On first deploy, the Pages project `satsday-web-fe` is auto-created.

## Custom domain (sats.day)

1. CF Dashboard → Pages → satsday-web-fe → Custom domains
2. Add `sats.day` and `www.sats.day`
3. CF will auto-configure DNS if sats.day is on Cloudflare

## Related

- Backend API: [satsday-api-be](https://github.com/CeyLabs/satsday-api-be)
- API base: `https://api.sats.day`
