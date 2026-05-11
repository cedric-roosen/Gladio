# Gladio

**Veni. Vidi. Vicerunt.**

Live tournament management and spectator platform for WKF Kumite karate.

[![Deploy to GitHub Pages](https://github.com/yourusername/gladio/actions/workflows/deploy.yml/badge.svg)](https://github.com/yourusername/gladio/actions/workflows/deploy.yml)

## Features

- Real-time WKF scoring: Yuko, Waza-ari, Ippon, Senshu, Kansa
- 5-step penalty cycle: W → W2 → HC → HC2 → H
- Single-elimination bracket with automatic bye handling
- WKF-correct repechage: traces every fighter on the finalist's full path
- Live spectator view with QR code (BroadcastChannel cross-tab sync)
- Final standings, match statistics, club rankings
- CSV import/export, print-ready PDF report
- Zero dependencies — one HTML file, works offline

## Usage

Open `index.html` in any modern browser. No build step, no server required.

For live spectator sync across devices, host on any static server or GitHub Pages.

**Live demo:** https://yourusername.github.io/gladio/

**Landing page:** https://yourusername.github.io/gladio/landing/

## Repo structure

```
gladio/
├── index.html          ← tournament app (self-contained)
├── landing/
│   └── index.html      ← marketing landing page
├── docs/
│   ├── brand-brief.md
│   ├── prd.md
│   └── screenshots/
└── .github/
    └── workflows/
        └── deploy.yml  ← GitHub Pages auto-deploy
```

## Tech Stack (current)

Single HTML file — HTML + CSS + vanilla JS + localStorage

## Planned Stack (production)

- Next.js 14+ (App Router)
- TypeScript
- Supabase (Realtime for live sync, PostgreSQL for data)
- Tailwind CSS
- Zustand (client state)

## WKF Rules

Implements WKF Kumite Rules 2025 Edition:
- Point types, Senshu, Kansa, penalty cycle, Hansoku
- Repechage logic per official bronze medal bracket rules

## Brand

Gladio — named after the Roman gladio sword.  
*Veni. Vidi. Vicerunt.* — I came. I saw. They won.

Built in Belgium. Scaling across Europe.

## License

MIT
