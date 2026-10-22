# RozBudget — Your daily income budget, tracked

A personal finance tracker built around one simple idea: **your monthly income ÷ the days in the month = your daily budget.** RozBudget tells you that number every morning, tracks what you spend against it through the day, and closes with a nightly budget-vs-spent summary — plus one dashboard that shows where the money actually goes.

Made for India: ₹ everywhere, Indian number formatting (en-IN), and import parsers for ICICI, Kotak, SBI, HDFC, Slice and generic UPI alerts.

## How it works

- **Setup** — enter your monthly income once (Settings). Daily budget = income ÷ days in the current month, rounded.
- **Today card** — greeting, today's budget, spent so far, remaining, and a progress bar that turns amber as you approach the limit and red when you cross it.
- **Add a transaction** — amount, note/merchant, method (UPI / Card / Cash / Bank), money in or out. The category is auto-suggested from the note (Swiggy → Food, Uber → Transport, Netflix → Subscriptions, a UPI payment to a person's name → Transfers…) and can be changed before saving.
- **Last night's summary** — yesterday's budget vs spent, and whether you were under or over, and by how much.
- **Dashboard** — this month's money in / out / net, a category breakdown with bars, a last-7-days spend chart with your daily budget drawn as a line, and a day-by-day list for the month with over-budget days marked red.
- **Backup** — export/import everything as a JSON file; clear all data anytime.

## Automatic tracking (import)

Indian banks can't be connected directly without the Account Aggregator framework, so RozBudget tracks automatically from the alerts and statements you already receive:

1. **Paste an alert** — copy any bank/UPI SMS or email alert into the Import box (several at once, separated by a blank line). RozBudget extracts the amount, debit/credit direction, merchant (from `at …`, `to …` or `Info:` narrations, including `UPI/MERCHANT/…` formats) and the date, categorizes it, and adds it. Duplicates (same amount + note + minute) are skipped.
2. **Statement CSV** — upload an exported statement from ICICI, Kotak, SBI, PhonePe or GPay. Date, narration, debit and credit columns are matched by header name; header/total rows are skipped and every row is categorized.
3. **Demo data** — one tap loads ~29 realistic sample transactions from the last 10 days (and a ₹30,000 sample income, only if you haven't set one) so the dashboard comes alive immediately. Clear it from Settings whenever you're ready to use your real numbers.

## Privacy

Everything runs in your browser. Data lives only in `localStorage` (key `rozbudget_v1`) on your device — no account, no server, no uploads. Use the JSON backup to move data between devices.

## Tech

Zero-build static site: a single self-contained `index.html` (inline CSS + JS, no external dependencies, no CDNs). Open the file in a browser, or deploy the folder to any static host (a `vercel.json` with security headers is included).

The demo domain in `robots.txt` / `sitemap.xml` (`rozbudget.vercel.app`) is a placeholder — update it after deploying.
