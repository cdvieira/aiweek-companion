# AI Week 2026 Companion

A lightweight, installable PWA companion for the AI Week 2026 conference in Milan.

Live: https://cdvieira.github.io/aiweek-companion/

## What it does

Browses all 534 sessions across the four conference days with a personal "fit" score (1-5) per session so you can quickly see what's worth attending. Works offline once installed.

## Install on mobile

- **iOS (Safari)**: open the live URL, tap the Share icon, choose *Add to Home Screen*.
- **Android (Chrome)**: open the live URL, open the menu (⋮), choose *Install app* / *Add to Home screen*.

Launch from the home-screen icon to get a fullscreen, app-like experience.

## Customize your pick scores (fork-friendly)

All session data — including the `fit` field that drives the pick score — lives in [`sessions.json`](./sessions.json).

To tailor it to your own interests:

1. Fork this repo to your own GitHub account.
2. Edit `sessions.json` — change the `"fit"` value (1–5) on any session.
3. Enable GitHub Pages on your fork: **Settings → Pages → Source: Deploy from branch → `main` / root**.
4. Your version will be live at `https://<your-user>.github.io/aiweek-companion/`.

### Fit score legend

| Score | Meaning |
|------:|---------|
| 5 | Perfect fit. Don't miss. |
| 4 | Strong match for your goals. |
| 3 | Relevant — worth attending if free. |
| 2 | Tangential. Only if curious. |
| 1 | Skip. Off-topic for you. |

## Project structure

```
index.html            App shell + UI (vanilla JS, no build step)
sessions.json         Session data + per-session fit scores (edit me)
manifest.webmanifest  PWA manifest
sw.js                 Service worker (offline caching)
icon-*.png            PWA icons
```

No build, no dependencies, no backend. Just static files served by GitHub Pages.

## Data source

Session schedule is derived from the public AI Week 2026 agenda at https://app.aiweek.it. All content (titles, speakers, stages) is publicly available conference information.
