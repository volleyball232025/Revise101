# Quran Revision AI — responsive memorization & revision tracker

A Cloudflare Workers + D1 app designed for desktop and phone.

## Features
- Account signup/login with PBKDF2 password hashing (100,000 iterations for Cloudflare Workers compatibility).
- Initial onboarding: choose memorized Surahs and rate each 1–6 stars.
- Surah detail: rate individual ayahs 1–6, mark weak ayahs, keep Surah-specific notes, and log "Read today" or a custom last-read date.
- Home: overall strength ring, quick Quran activity comparisons, today's homework, weakest/strongest Surah chart, recent Surahs.
- Homework planner: prioritizes weak/low-rated/stale material, keeps assignments in Quran order, and fits a selected time target. It learns from actual completion time.
- Stats: total ayahs memorized, weak ayahs, reading activity for 7 days/month/year/lifetime, and strength rankings.
- Customizable home: show/hide dashboard cards in Settings.

## Cloudflare setup
1. Push the CONTENTS of this folder to a GitHub repository (package.json should be at repository root).
2. Create a D1 database named `quran-revision-db`.
3. Copy its database ID into `wrangler.jsonc`, replacing `REPLACE_WITH_YOUR_D1_DATABASE_ID`.
4. Run `schema.sql` once in the D1 console.
5. Connect the GitHub repository to Cloudflare Workers and deploy. Root directory should be `/`.

No custom domain is required; the generated `workers.dev` URL works.
