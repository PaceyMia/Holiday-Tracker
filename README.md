# 🌴 Holiday Tracker

A mobile-first expense tracker for all-inclusive resort holidays. Built as a single HTML file — no app store, no backend, no subscription. Open the link, save it to your home screen, and start tracking.

**Live app:** [paceymia.github.io/Holiday-Tracker/index.html](https://paceymia.github.io/Holiday-Tracker/index.html)

---

## What it does

Resort holidays often come with a daily room credit for food and drinks. This app helps you track exactly how much of that credit you've used each day, what you've spent out of pocket on drinks and coffees, and what you've charged to the room that you'll need to settle at checkout — all in one place, right at the table.

At checkout, you'll know exactly how much cash to bring.

---

## Features

- **Daily food budget tracking** — set your room credit per person and number of people, and the app tracks your remaining balance in real time
- **Lunch and dinner split** — see how much of your budget went to each meal
- **Drinks and coffees** — tracked separately as out-of-pocket spend, never touching your food budget
- **Room charges** — log souvenirs, spa treatments, activities and anything else charged to the room
- **Tips** — quick-add during receipt entry, counted as out of pocket
- **Checkout total** — a running total of everything you'll need to pay at checkout, shown in local currency and AUD with a live exchange rate
- **Live FX conversion** — fetches the current rate on load from the ECB via frankfurter.app, falls back gracefully if offline
- **Quick Add mode** — enter food, drinks and tip as three numbers and save in seconds at the table
- **Line by Line mode** — add individual items with names for a full itemised record
- **Receipt photo linking** — attach a Google Drive, iCloud or Dropbox link to each receipt for evidence
- **Full history** — scrollable day-by-day view grouped by restaurant, with per-day summaries
- **Charts** — daily spend vs budget bar chart, food/drinks/room stacked chart, lunch vs dinner split, and most expensive days
- **Email backup** — sends a full summary and CSV to your email using your phone's mail app. Prompted automatically after dinner, or triggered manually anytime
- **CSV export** — download a clean spreadsheet of all entries at the end of your trip
- **Setup screen** — configure your trip name, currency, budget, email and photo storage on first open. Change anything later via Settings
- **Works offline** — once loaded the app works without internet (FX rate will use fallback)
- **One device** — all data lives in your phone's browser storage. No account, no sync, no cloud

---

## Getting started

### 1. Open the app

Visit the link above in your phone's browser.

### 2. Save to your home screen

**iPhone (Safari only):**
Tap the Share button → Add to Home Screen → Add

**Android (Chrome):**
Tap the three dots → Add to Home Screen → Add

### 3. Complete setup

On first open you'll be asked for:
- A trip name
- Your local currency (default FJD)
- Daily room credit per person and number of people sharing
- Your email address for backups
- Whether you want to store receipt photos (Google Drive, iCloud or Dropbox)

You can change any of this later by tapping **Settings** in the top right corner of the app.

---

## Adding expenses

Tap **Add Receipt**, enter the restaurant or shop name and date (defaults to today), then pick a type:

| Type | What it means |
|---|---|
| 🍽️ Lunch | Food counts toward your daily budget. Drinks and tip are out of pocket |
| 🌙 Dinner | Same as Lunch |
| ☕ Drinks Only | Coffees, poolside drinks, anything outside a meal. Always out of pocket |
| 🛍️ Room Charge | Souvenirs, spa, activities. Tracked separately for checkout |

Tap a type to expand it and enter amounts. In **Quick Add** mode enter totals (Food, Drinks, Tip). Switch to **Line by Line** for itemised entries with individual names.

---

## The Today tab explained

| Card | What it shows |
|---|---|
| Daily Remaining | How much food budget is left today. Goes amber then red as you spend |
| Lunch / Dinner | How much food budget was used at each meal |
| Drinks and Coffees Today | Out-of-pocket drinks spend today |
| Room Charges Today | Items charged to the room today |
| Total Drinks (Trip) | All drinks across the whole stay, in local currency and AUD |
| Total Room Charges (Trip) | All room charges across the whole stay, in local currency and AUD |
| **Total to Pay at Checkout** | Drinks total + Room charges total combined. This is the number to bring to checkout |

---

## Backing up your data

All data lives on your phone. If you clear your browser or switch devices, it's gone.

**Tap Email Me a Backup** on the Today tab at the end of each day. This opens your mail app with a full daily summary and complete CSV pre-filled — just hit send. You'll also be prompted automatically after saving a dinner receipt.

You can also **Download CSV** from the History tab at any time.

---

## Important

> **This app stores data on one device only.** Everything is saved in your phone's browser storage (`localStorage`). Opening the link on a different phone or browser will show a fresh empty app. Pick one phone between you and stick to it for the whole trip.

---

## Currency and exchange rate

The app fetches a live mid-market rate from [frankfurter.app](https://frankfurter.app) (European Central Bank data) on every page load. The rate used is shown next to the AUD conversion. If the fetch fails — no signal at the restaurant, for example — it falls back to a recent hardcoded rate and labels it clearly.

The home currency is always **AUD**. The local currency defaults to **FJD** but can be changed in Settings to any currency code Frankfurter supports.

---

## Photo storage

During setup you can choose where to store receipt photos:

**Google Drive** — best for Android users and anyone with a Google account. Upload to a shared folder, get a shareable link, paste it into the app.

**iCloud Drive** — best for iPhone users. Upload to Files app, tap Share → Copy iCloud Link, paste it in.

**Dropbox** — works on any phone. Upload, tap the three dots, Create link, paste it in.

Each receipt can have one photo link attached. Links are saved with entries and shown in History.

---

## Files in this repo

| File | Description |
|---|---|
| `index.html` | The complete app — everything in a single file |

---

## Tech notes

- Pure HTML, CSS and vanilla JavaScript — no frameworks, no build step
- [Montserrat](https://fonts.google.com/specimen/Montserrat) via Google Fonts
- [Tailwind CSS](https://tailwindcss.com) via CDN (minimal utility use)
- [frankfurter.app](https://frankfurter.app) for live exchange rates (free, no API key)
- Canvas API for charts — no external chart library
- `mailto:` for email backup — no third-party service needed
- `localStorage` for all persistence

---

## Built with

This app was designed and built entirely through conversation with [Claude](https://claude.ai) by Anthropic. Every feature, bug fix, audit and design decision was made iteratively in a single chat session.

---

## License

Personal use. Feel free to fork and adapt for your own holiday.
