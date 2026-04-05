# satsday-web-fe

Frontend for [sats.day](https://sats.day) — CAPTCHA solving marketplace on Bitcoin Lightning.

## Pages

| Path         | Description                                      |
|--------------|--------------------------------------------------|
| `/`          | Landing page (landing page for buyers + solvers) |
| `/app/`      | Solver app — TG login, CAPTCHA queue, earnings   |

## Stack

- Pure HTML/CSS/JS — zero build step, no dependencies
- Cloudflare Pages (auto-deploy on push via GitHub Actions)
- Google Fonts: JetBrains Mono + Outfit

## Deploy

Push to `main` → GitHub Actions → Cloudflare Pages auto-deploy.

First-time setup: add `CLOUDFLARE_API_TOKEN` as a GitHub Actions secret.
The Pages project `satsday-web-fe` is created automatically on first deploy.

## App flow

1. User visits `/app/` → Telegram Login Widget
2. Authenticates via @SatsDayBot
3. Dashboard: balance, accuracy, solved count
4. "Start Solving" → fetches tasks from `api.sats.day/solver/task`
5. Solve image/text CAPTCHAs → earn sats instantly
6. "Add Credits" → BTCPay Lightning invoice for buyers
7. Withdraw via `/withdraw` in @SatsDayBot

## Environment

The app hits `https://api.sats.day` directly from the browser.
No server-side rendering — fully static.

## Related

- Backend API: [satsday-api-be](https://github.com/CeyLabs/satsday-api-be)
- Telegram bot: [@SatsDayBot](https://t.me/bitcoindeepabot)
