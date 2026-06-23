# WC 2026 — Full Project Context

## What this app does
A live mobile-friendly web app that tracks the FIFA World Cup 2026 group stage standings
and automatically forecasts the Round of 32 knockout bracket based on current standings.
Built as a single HTML file, works on iPhone and desktop, no backend needed.

---

## Live URL
🌍 https://yamo01.github.io/wc2026/

---

## Files
```
/Users/yamo/Documents/ClaudeCode/WC2026/
├── index.html     ← the entire app (HTML + CSS + JS in one file)
├── DEPLOY.md      ← quick deploy cheatsheet
└── PROJECT.md     ← this file
```

---

## How the app works

### Data source
- **ESPN unofficial API** — free, no API key needed, no registration
- URL: `https://site.api.espn.com/apis/v2/sports/soccer/fifa.world/standings`
- Fetched on page load + every 60 seconds automatically
- Returns all 12 groups with teams, points, goal difference, advancement status

### Tech stack
- Pure HTML + CSS + JavaScript (no framework, no build step, no dependencies)
- Works offline after first load (data just won't refresh)
- Mobile-first design, tested on iPhone Safari

### App structure (inside index.html)
- **Groups tab** — live standings for all 12 groups (A–L), color-coded by position
- **Bracket R32 tab** — all 16 Round of 32 matchups using the official FIFA pairing matrix
- **3rd place tab** — all 12 third-place teams ranked, with cut line showing which 8 advance
- **Bottom nav + top nav** — both wired up for easy mobile navigation
- **Auto-refresh** every 60 seconds, manual refresh button top right

### FIFA R32 bracket pairing map (hardcoded, official)
| Match | Pairing |
|-------|---------|
| M73 | 2A vs 2B |
| M74 | 1E vs best 3rd (A/B/C/D/F) |
| M75 | 1F vs 2C |
| M76 | 1C vs 2F |
| M77 | 1I vs best 3rd (C/D/F/G/H) |
| M78 | 2E vs 2I |
| M79 | 1A vs best 3rd (C/E/F/H/I) |
| M80 | 1L vs best 3rd (E/H/I/J/K) |
| M81 | 1D vs best 3rd (B/E/F/I/J) |
| M82 | 1G vs best 3rd (A/E/H/I/J) |
| M83 | 2K vs 2L |
| M84 | 1H vs 2J |
| M85 | 1B vs best 3rd (E/F/G/I/J) |
| M86 | 1J vs 2H |
| M87 | 1K vs best 3rd (D/E/I/J/L) |
| M88 | 2D vs 2G |

### 3rd place logic
- All 12 third-place teams collected (one per group)
- Sorted by: points → goal difference → goals for
- Top 8 advance to R32, bottom 4 are eliminated
- The specific slot each 3rd-place team fills depends on which groups they came from (FIFA matrix)

---

## Tournament format
- 48 teams, 12 groups of 4
- Top 2 from each group (24 teams) + best 8 third-place teams = 32 teams in R32
- R32 runs Jun 28 – Jul 3 2026
- Then R16, QF, SF, Final

---

## GitHub repository
- Repo: https://github.com/yamo01/wc2026
- Branch: main
- GitHub Pages: enabled, auto-deploys on every push to main

---

## How to deploy updates

### Terminal (fastest)
```bash
cd /Users/yamo/Documents/ClaudeCode/WC2026
git add index.html
git commit -m "describe your change"
git push
```

### Browser only (no terminal)
1. Go to https://github.com/yamo01/wc2026
2. Click index.html → ✏️ pencil icon → edit → Commit changes

### Netlify drag & drop
1. Login at netlify.com
2. Drag WC2026 folder onto your site's Deploys tab

---

## How to continue development with Claude
Open a new Claude Code session in this folder:
```
/Users/yamo/Documents/ClaudeCode/WC2026
```
Tell Claude: "Read PROJECT.md first" — it has everything needed to pick up where we left off.

### Ideas for future features
- Push notifications when a match starts or result drops (Alerts tab)
- R16 / QF / SF bracket once R32 is complete
- Tap a match to see head-to-head stats
- Dark mode toggle
- Auto-detect when the group stage is over and switch to full bracket view
- Add actual R32 match results as they come in (ESPN scoreboard API)
