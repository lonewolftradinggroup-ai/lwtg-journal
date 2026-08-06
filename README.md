# LWTG Trade Journal

**Lone Wolf Trading Group 🐺 — Monthly Trade Calendar & Journal**

A calendar-based trade journal that pulls directly from your Google Sheet, shows all trades by day, and lets you filter by strategy and instrument. Click any day to see a full breakdown of trades, P&L, win rate, and per-strategy performance.

---

## 🚀 Quick Start

### ⚠️ GitHub Pages — Limited Support

The GitHub Pages hosted version at:

**[https://lonewolftradinggroup-ai.github.io/lwtg-journal/](https://lonewolftradinggroup-ai.github.io/lwtg-journal/)**

is available for reference but **trade data will not load** due to a Google Apps Script cross-origin (CORS) limitation. GitHub Pages cannot fetch data directly from GAS web apps. Use Option A (local) below for full functionality.

---

### Option A — Local (Recommended)

Full functionality. Run locally in under 60 seconds.

**Step 1 — Download `journal.html`** from this repo.

**Step 2 — Start a local web server**

Open a terminal in the folder containing the file and run:
```
python -m http.server 8080
```

> ⚠️ You must open the app via `http://localhost:8080` — not by double-clicking the file. Opening `journal.html` directly uses `file://` which blocks connections to Google Sheets.

**Step 3 — Open in Chrome**
```
http://localhost:8080/journal.html
```

On first launch the Connect dialog appears — paste your GAS /exec URL and click Save & Connect. The URL is remembered in your browser.

---

## ⚙️ Changing Your GAS URL

Click the **⚙ gear icon** in the top-right header at any time to update your GAS /exec URL. Your URL is stored in your browser — it never leaves your machine.

To find your GAS URL: Apps Script → Deploy → Manage Deployments → copy the URL ending in `/exec`.

---

## 📋 Journal Overview

| Element | What it shows |
|---|---|
| **Month PnL** | Total net P&L for the current month |
| **Trades** | Total closed trades this month |
| **Win Rate** | TP / total trades |
| **Best Day** | Highest single-day P&L |
| **Worst Day** | Lowest single-day P&L |
| **Strategy pills** | Monthly breakdown by MITS / QC Signals / QC Trend |
| **Calendar** | Each day shows trade count, W/L, and net P&L |
| **Day panel** | Click any day for full trade-by-trade detail |

---

## 🔍 Filters

**Strategy:** ALL · MITS · QC Signals · QC Trend

**Instrument:** ALL · MES · MNQ · M2K · MGC · MYM · MCL

Filters apply to the calendar view and day detail panel simultaneously.

---

## 📅 Navigation

Use **◀ Prev** / **Today** / **Next ▶** to move between months. The calendar always shows the filtered view for the selected month.

---

## 🎨 Instrument Colors

| Instrument | Color |
|---|---|
| MES | Green |
| MNQ | Blue |
| M2K | Orange |
| MGC | Gold |
| MYM | Purple |
| MCL | Amber |

---

## ❓ Troubleshooting

| Problem | Fix |
|---|---|
| "Failed to fetch" or "Sheets poll failed" on GitHub Pages | Expected — GAS CORS limitation. Use local hosting instead (Option A above) |
| "JSONP timeout" | GAS deployment may be stale — redeploy to existing deployment and retry |
| Connect dialog keeps appearing | GAS URL not saved — paste your /exec URL and click Save & Connect |
| Calendar shows no trades | Check that your GAS URL is correct and the TradeLog sheet has data |
| App won't load | You opened `journal.html` directly — use `http://localhost:8080/journal.html` instead |
| Trades missing for a date | Webhook timeouts may have caused gaps — check TradingView alert log and add manual entries to TradeLog |

---

## 📁 Files

| File | Description |
|---|---|
| `journal.html` | The Trade Journal app — safe to share, no credentials |
| `index.html` | Legacy file — use `journal.html` instead |

---

*Not financial advice. 🐺 Lone Wolf Trading Group*
