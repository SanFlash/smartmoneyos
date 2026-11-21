# SmartMoney OS

A privacy-first, local-first personal finance dashboard for Indian Rupees (INR). No Supabase, server database, account, bank integration, or API keys are required.

## Run locally

1. Clone this repository.
2. Open the project folder with a local static server (recommended) or deploy the root directory to Vercel.
3. Open the app in a modern browser. The local IndexedDB database is created automatically.

For local development, for example:

```bash
python -m http.server 8000
```

Then open http://localhost:8000.

## Local data and privacy

- All transactions, budgets, and savings goals are stored in the browser's IndexedDB database named `SmartMoneyOS`.
- No finance records are sent to a backend. The app does not require Supabase credentials or a login.
- A service worker caches the application shell so it can reopen offline after the first successful visit.
- Data is isolated to the browser profile and origin on the current device. It does not sync between devices or browsers.
- Use **Settings → Export full backup (JSON)** before clearing browser data, changing devices, or uninstalling the browser.
- Use **Settings → Import backup** to restore a previously exported JSON backup.
- CSV export is available for transactions.

## Features

- Manual transaction entry for expenses, income, investments, savings, and transfers.
- Captures platform/merchant, purpose, payment method, account, date, recurrence, and notes.
- Monthly category budgets and savings goals with contribution tracking.
- Salary-first expense planner: configurable take-home pay, savings target above ₹9,000, and percentage-based spending envelopes by category. Recorded income overrides the configured salary for that month.
- Monthly net position, spending breakdown, allocation view, and searchable transaction ledger.
- Full JSON backup/restore and CSV export.
- Responsive dark fintech dashboard and offline application-shell caching.

## Accounting rules

- Expenses are consumption outflows.
- Investments and savings are shown separately from expenses.
- Transfers are excluded from consumption and net-position calculations to avoid double counting.
- Dashboard figures reflect manually entered records, not verified bank balances, investment valuations, or payment confirmations.

## Important

This is a personal record-keeping tool, not a bank, payment processor, tax product, or regulated financial adviser. Do not enter bank passwords, UPI PINs, OTPs, card CVVs, or other authentication secrets. Browser-local data is not encrypted by this application; protect your device account and keep backups in a secure location.
