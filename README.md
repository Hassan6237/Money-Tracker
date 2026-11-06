# Ledger — Personal Expense Tracker

**▶ Live demo: [hassan6237.github.io/Money-Tracker](https://hassan6237.github.io/Money-Tracker/)**

A lightweight, single-page expense tracker built with vanilla JavaScript, HTML, and CSS. No build step, no framework — just open it in a browser. All data is stored locally in the browser via `localStorage`, so nothing you enter is sent to a server. User input is HTML-escaped before rendering to prevent XSS.

## Features

- **Dashboard** — At-a-glance stats (total spent, this month's spend, transaction count, average per transaction), a list of recent expenses, and a category breakdown pie chart.
- **All Expenses** — A sortable, filterable table of every expense (filter by category and date range), with inline edit and delete actions.
- **Add / Edit Expense** — A validated form for logging expenses with title, amount, date, category, and optional notes, plus a live category preview.
- **Analytics** — Spending by category (bar chart), category distribution (doughnut chart), monthly spending trend (line chart), and a detailed category breakdown list.
- **Responsive design** — Collapsible sidebar with a mobile hamburger menu for smaller screens.
- **Persistent storage** — Expenses are saved to `localStorage` under the key `ledger_expenses`, so data survives page reloads.
- **Currency formatting** — Amounts are formatted in PKR (Rs) using `en-PK` locale formatting.

## Categories

Food & Dining · Transport · Utilities · Shopping · Entertainment · Health · Education · Travel · Other

Each category has an associated color and emoji used throughout the charts and UI.

## Project Structure

```
.
├── index.html   # App markup — dashboard, expenses table, add/edit form, analytics views
├── style.css    # All styling
└── app.js       # App logic — state, routing, rendering, charts, form handling
```

## Getting Started

No installation or build tools required.

1. Download or clone the three files (`index.html`, `style.css`, `app.js`) into the same folder.
2. Open `index.html` in a web browser.

That's it — the app runs entirely client-side.

## Dependencies

Loaded via CDN in `index.html` — no local install needed:

- [Chart.js 4.4.1](https://www.chartjs.org/) — used for the pie, bar, doughnut, and line charts.
- [Google Fonts](https://fonts.google.com/) — Plus Jakarta Sans and IBM Plex Mono.

## How It Works

- **Routing**: A simple view-switcher (`navigate()`) toggles which section (`dashboard`, `expenses`, `add`, `analytics`) is visible and re-renders that view's content.
- **State**: All expenses live in an in-memory `expenses` array, loaded from and saved to `localStorage` on every change.
- **Charts**: Chart.js instances are created/destroyed as needed when navigating between views to avoid duplicate or stale charts.
- **Validation**: The add/edit form validates title, amount (> 0), date, and category before saving, with inline error messages.
- **Delete confirmation**: Deleting an expense opens a confirmation modal before removing it.

## Data Storage & Privacy

All expense data stays in your browser's `localStorage` — nothing is sent to a server. Clearing your browser data or using a different browser/device will not carry over your expenses.

## Browser Support

Works in any modern browser with support for `localStorage`, ES6+ JavaScript, and `crypto.randomUUID()` (with a fallback ID generator for older browsers).

## 👤 Author

**Hassan Ali**, BSc Computer Science (Year in Industry) student at the University of Kent<br/>
[GitHub](https://github.com/Hassan6237) · [LinkedIn](https://www.linkedin.com/in/hassan623)
