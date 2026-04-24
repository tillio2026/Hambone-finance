# Hammbone Finance 💖

A personal finance PWA — paychecks, taxes, bills, savings, and a 0–100 financial health score. Designed for a single filer in Camp Hill, PA, paid bi-weekly.

Runs entirely in the browser — all data is stored in `localStorage` on the device, so each person who installs it gets a completely separate instance. Protected by a 4-digit passcode on first launch.

## Features

- **Income tab** — log each bi-weekly paycheck, running YTD total, projected annual
- **Taxes tab** — enter per-category withholding from your paystub (Federal, Social Security, Medicare, PA 3.07%, Local EIT 1%, LST). Tax rate auto-adjusts as YTD income crosses federal brackets. Shows surplus/deficit vs. projected liability
- **Bills tab** — manually entered bills, "bills vault" deposits, monthly/weekly toggle, coverage progress bar per bill
- **Savings tab** — SoFi-style named vaults with categories and goals
- **Health Score tab** — 0–100 credit-score-style gauge blending income consistency, tax discipline, bills coverage, surplus rate, and savings cushion
- **Installable** — Add to Home Screen on iOS/Android for native-app feel
- **Private** — data never leaves the device. Export/import JSON for backups

## Deploy to GitHub Pages (short version)

You already did this with Nurse X, so just the commands:

```bash
cd ~/path/to/this/folder

git init
git add .
git commit -m "Initial Hammbone Finance"
git branch -M main

# Create a new repo on github.com called hammbone-finance (empty, no README)
git remote add origin https://github.com/<your-username>/hammbone-finance.git
git push -u origin main
```

Then on GitHub:

1. Go to **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)**, click **Save**
4. Wait ~1 minute, then your app is live at `https://<your-username>.github.io/hammbone-finance/`

## Install on iPhone

1. Open the GitHub Pages URL in **Safari** (must be Safari for PWAs on iOS)
2. Tap the **Share** icon
3. Tap **Add to Home Screen**
4. The Hammbone Finance icon appears on your home screen — tap it to open full-screen

## Install on Android

1. Open the URL in **Chrome**
2. Tap the three-dot menu → **Install app** (or accept the install banner)

## For you and your girlfriend

Each of you installs the PWA independently on your own phone. On first launch, each of you sets your own 4-digit passcode. Your data is stored on your phone only — nothing is shared, synced, or visible to the other person.

If you ever want to move to another device, use **Settings → Export Data** to download a JSON backup, then **Import** on the new device.

## Tax config (2025, single filer, Camp Hill PA)

- Federal: standard deduction $15,000; 2025 brackets 10 / 12 / 22 / 24 / 32 / 35 / 37%
- Social Security: 6.2% up to wage base $176,100
- Medicare: 1.45% on all wages + additional 0.9% over $200,000
- Pennsylvania: flat 3.07%
- Local EIT: 1% (Camp Hill Borough 0.5% + Camp Hill School District 0.5%)
- LST: $52/year ($2 per bi-weekly pay)

Update `TAX_CONFIG` at the top of the `<script>` block in `index.html` when IRS brackets change each year.

## File structure

```
index.html       main app (UI + all logic)
manifest.json    PWA manifest for "Add to Home Screen"
sw.js            service worker for offline support
icon-192.png     app icon (Android home screen)
icon-512.png     app icon (splash screen / stores)
favicon.png      browser tab icon
README.md        this file
```
