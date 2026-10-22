# RozBudget — Your daily income budget, tracked

A personal finance tracker built around one simple idea: monthly income divided by the days in the month = your daily budget. RozBudget tells you that number every morning, tracks what you spend against it through the day, and closes with a nightly budget-vs-spent summary — plus one dashboard that shows where the money actually goes.

Made for India: rupee formatting (en-IN) and import parsers for ICICI, Kotak, SBI, HDFC, Slice and generic UPI alerts.

## Automatic tracking (import)

Indian banks cannot be connected directly without the RBI Account Aggregator framework, so RozBudget tracks from the alerts and statements you already receive: paste bank/UPI SMS or email alerts into the Import box, or upload a statement CSV. Demo data included.

## Privacy

Everything runs in your browser; data lives only in localStorage on your device. No account, no server, no uploads.

## Tech

Zero-build static site: a single self-contained index.html (inline CSS + JS, no external dependencies).