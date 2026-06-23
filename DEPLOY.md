# WC 2026 — How to update & deploy

## Live URL
🌍 https://yamo01.github.io/wc2026/

---

## Option A — GitHub (terminal, 3 commands)

Open Terminal, paste this:

```bash
cd /Users/yamo/Documents/ClaudeCode/WC2026
git add index.html
git commit -m "update"
git push
```

Site refreshes in ~30 seconds.

---

## Option B — GitHub (no terminal, browser only)

1. Go to https://github.com/yamo01/wc2026
2. Click **index.html**
3. Click the ✏️ pencil icon (top right)
4. Make your changes
5. Click **"Commit changes"** (green button)

Site refreshes in ~30 seconds.

---

## Option C — Netlify (drag & drop, easiest)

1. Go to https://netlify.com and log in
2. Find your site in the dashboard
3. Go to **Deploys** tab
4. Drag the `WC2026` folder onto the page

Done instantly.

---

## Where is the app file?

📁 /Users/yamo/Documents/ClaudeCode/WC2026/index.html

That's the only file. Edit it, then deploy with any option above.

---

## Data source

Live scores come from ESPN's free API — no key needed, auto-refreshes every 60 seconds.
`https://site.api.espn.com/apis/v2/sports/soccer/fifa.world/standings`
