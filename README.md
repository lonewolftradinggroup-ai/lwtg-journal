# LWTG Trade Journal

**Lone Wolf Trading Group 🐺 — Monthly Trade Calendar & Journal**

A calendar-based trade journal that pulls directly from your Google Sheet, shows all trades by day, and lets you filter by strategy and instrument. Click any day to see a full breakdown of trades, P&L, win rate, and per-strategy performance.

---

## 🚀 Quick Start — Two Ways to Run

### Option A — GitHub Pages (recommended for most users)

No download, no setup. Just open:

**[https://lonewolftradinggroup-ai.github.io/lwtg-journal/journal.html](https://lonewolftradinggroup-ai.github.io/lwtg-journal/journal.html)**

On first launch the Connect dialog asks for your GAS /exec URL. Paste it, click Save & Connect. Done. The URL is remembered in your browser.

> This is all most users need. The journal shows your full trade calendar, monthly stats, and day-by-day breakdowns from your Google Sheet.

---

### Option B — Local

The journal is read-only (no Ghost webhooks needed), so Option A works for almost everyone. Run locally only if you need to work offline or want to modify the file.

**Step 1 — Download `index.html`** from the [latest release](https://github.com/lonewolftradinggroup-ai/lwtg-mits-system/releases).

**Step 2 — Start a local web server**

Open a terminal in the folder containing the file and run:
```
python -m http.server 8080
```

> ⚠️ You must open the app via `http://localhost:8080` — not by double-clicking the file. Opening `index.html` directly uses `file://` which blocks connections to Google Sheets.

**Step 3 — Open in Chrome**
```
http://localhost:8080/index.html
```

On first launch the Connect dialog appears — paste your GAS /exec URL and click Save & Connect.

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

**Instrument:** ALL · MES · MNQ · M2K · MGC · MYM

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

---

## ❓ Troubleshooting

| Problem | Fix |
|---|---|
| Connect dialog keeps appearing | GAS URL not saved — paste your /exec URL and click Save & Connect |
| Calendar shows no trades | Check that your GAS URL is correct and the TradeLog sheet has data |
| App won't load | You opened `index.html` directly — use `http://localhost:8080/index.html` instead |
| Trades missing for a date | Webhook timeouts may have caused gaps — check TradingView alert log and add manual entries to TradeLog |

---

## 📁 Files

| File | Description |
|---|---|
| `index.html` | The Trade Journal app — safe to share, no credentials |

---

*Not financial advice. 🐺 Lone Wolf Trading Group*
