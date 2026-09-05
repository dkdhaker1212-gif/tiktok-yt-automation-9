# tiktok-yt-automation-9 — "Dinero Claro"

Daily automated re-upload: TikTok source → YouTube (long-form, Spanish).

- **Source:** TikTok `@las_finanzas_personales` (Spanish personal-finance education)
- **Target channel:** "Dinero Claro" on `dhakerkrishti@gmail.com`
- **Format:** long-form (`content_mode: longform`), 45s–30min window, source aspect kept
- **Schedule:** 1 upload/day at **13:00 UTC** (7 AM Mexico City / 8 AM Bogotá / 10 AM Buenos Aires / 3 PM Madrid) — self-scheduled via GitHub Actions `schedule:` cron in `.github/workflows/upload.yml`
- **Picking:** `popular_only` — always the most-viewed unposted source video
- **SEO:** `seo_language: es` — Gemini writes Spanish title / description / tags from the video's audio + frames; Anthropic then template fallback
- **Edit:** loudnorm, light sharpen/colour, small "Dinero Claro" corner badge (`assets/brand_badge.png`)
- **Category:** 27 (Education)

## Secrets (GitHub → Settings → Secrets → Actions)
- `CHANNEL_9_CLIENT_SECRET` — base64 of the OAuth desktop client JSON
- `CHANNEL_9_TOKEN` — base64 of the minted token JSON (scopes: youtube.upload + youtube.force-ssl)
- `GEMINI_API_KEY` — for AI SEO

## Manual run
Actions → "Channel 9 - Daily Upload" → Run workflow (`dry_run` / `force` inputs available).
