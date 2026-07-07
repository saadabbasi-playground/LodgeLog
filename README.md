# LodgeLog — Australian Tax & BAS Companion

A lightweight, installable PWA for tracking income, deductions and GST across the
Australian financial year. Runs entirely on-device — no backend, no accounts,
nothing leaves your phone.

## Features
- **Live tax estimate** — refund/payable meter using ATO resident brackets, LITO
  and Medicare levy (with low-income phase-in), for FY 2025-26 and FY 2026-27
- **Profile-aware suggestions** — deduction recommendations for employees,
  WFH workers, rideshare drivers and sole traders, based on ATO guidance
- **Expense log** — categories mapped to individual return labels (D2–D5, gifts,
  agent fees) and business categories, with work-use % apportionment
- **WFH calculator** — fixed rate (70c/hr) vs actual cost, with record-keeping rules
- **Car calculator** — cents/km (88c FY25-26 / 91c FY26-27, 5,000 km cap) vs
  logbook method, with double-claim protection on running costs
- **BAS helper** — quarterly G1 / 1A / 1B with net GST per quarter and due dates;
  rideshare-aware (GST from the first dollar, gross fares before platform fees)
- **Backup/restore** — JSON export & import; all data in localStorage

## Deploy to GitHub Pages (same as Ironlog)
1. Create a repo, e.g. `lodgelog`
2. Push these five files to the repo root:
   `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`
3. Settings → Pages → Deploy from branch → `main` / root
4. Open `https://<user>.github.io/lodgelog/` on your iPhone → Share → **Add to Home Screen**

## Updating tax rates
All rates live in the `FY` object at the top of the script in `index.html`.
Add a new year by copying a block and updating brackets/rates. Bump the
`CACHE` name in `sw.js` (e.g. `lodgelog-v2`) so installed devices pick up changes.

## Not modelled (by design — check with a tax agent)
HELP/HECS repayments, Medicare levy surcharge, franking credits, offsets other
than LITO, non-commercial loss quarantining, FBT, super contributions.
General information only — not tax advice.
