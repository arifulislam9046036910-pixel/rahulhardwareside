# Rahul Hardware — AI App Builder Prompt

Build a production-ready, mobile-first shop management app named **Rahul Hardware** for an Indian hardware and construction-materials shop. Use the supplied `index.html` as the current UI/feature reference; preserve its Bengali-first interface and the owner's requested layout. Do not replace it with a generic dashboard.

## Main screen and navigation
- Full-screen mobile home page with large, bold, easy-to-tap cards for Dashboard, Calculator, খাতা বুক (customer ledger), Items/Stock, and Billing.
- Keep the home page uncluttered. Do not show demo/demo mode labels, stock quantity summary cards, “সময়ের ধার-জমা (নেট)”, recent-bill empty-state filler, quick-action shortcuts, or shop-information paragraphs on the home page.
- Put Settings as a small gear icon at the top-right. Move reports, backup/restore, date-range controls, shop information, and secondary settings inside Settings.
- Use clear Bengali labels, readable typography, accessible contrast, responsive layout, and simple back navigation.

## Dashboard and date filters
- Show sales, estimated gross profit, and current total receivables/payables as clearly defined metrics.
- Date range selector must support Today, Yesterday, last 7 days, last 6 months, last 1 year, last 10 years, and custom from/to dates.
- Date filtering must calculate from actual saved transactions, not hard-coded/demo numbers.
- Distinguish “sales/profit during selected period” from “current outstanding customer balance”. If historical as-of balances are shown, calculate them from dated ledger entries and label them clearly.
- Do not invent data. Show zero/empty state only when the underlying database has no records.

## Items and stock
- Add, edit, search, and archive/delete items.
- Each item stores name, category, unit (KG, GRAM, CFT, BAG, TON, PCS, TRACTOR and configurable units), purchase cost, selling price, opening stock, current stock, and low-stock threshold.
- Items saved in Items/Stock must appear automatically in Calculator and Billing. Price and unit should auto-fill when selected.
- Stock changes must be recorded through purchases, sales, returns, and adjustments with a dated movement history. Prevent negative stock unless the owner explicitly enables it.

## Calculator
- Keep one compact calculator panel, not two separate large panels.
- Select a saved item or enter a manual item name and price.
- Automatically use the selected item's unit and selling price.
- If quantity is entered, calculate total amount. If amount is entered, calculate quantity. Avoid circular-update loops and use correct decimal precision.
- Support the item's actual unit; KG/GRAM conversion must be accurate (1000 grams = 1 kilogram). Do not force every item into KG/GRAM.

## Billing
- Create bills with customer, date/time, multiple line items, quantity, unit, rate, discount, tax if configured, and total.
- Save, view, edit/void with audit trail, print/export PDF, and share bill summary through WhatsApp.
- On bill save, update stock and customer ledger exactly once; protect against duplicate submissions.
- Cash/UPI/credit/split payment methods and payment status.
- PDF must contain shop name/contact details, bill number, date, customer, line items, totals, and payment status.

## Customer ledger (খাতা বুক)
- Customer-wise debit/credit entries, opening balance, payments, credit sales, running balance, due reminders, date filters, and printable statement.
- Keep historical ledger entries immutable; corrections should create adjustment entries.

## Reports, backup, and security
- Reports: daily/monthly/yearly sales, gross profit, stock valuation, item-wise sales, customer outstanding, expenses, and cash summary.
- Backup export and restore with validation, confirmation, and schema versioning.
- PIN/password lock, role-based access if multiple staff, and audit log.
- Data must persist across reloads and app restarts. Provide database migrations and safe backup/restore.

## Technical requirements
- Deliver complete source code, build/run instructions, and a signed Android APK/AAB build path.
- Prefer a maintainable stack (for example React + TypeScript + SQLite/local database, with optional secure cloud sync). If retaining the supplied HTML app, refactor into modules and add robust storage.
- For production multi-device use, implement authenticated backend, encrypted transport, access rules, and tested sync/conflict handling. Never claim cloud sync exists unless implemented and tested.
- Provide automated tests for calculations, unit conversions, billing, stock movements, date filters, ledger balances, backup/restore, and offline behavior.
- Include a clear setup guide. Do not insert fake sales/profit data into production.
- Before calling the app complete, run tests, verify Android build, test on a small-screen Android device, and report any remaining limitations honestly.

## Deliverables
1. Full editable source project.
2. Installable Android APK for testing and AAB for Play Store (if supported by the build environment).
3. PWA installable web build.
4. Database schema and migrations.
5. Build, signing, deployment, and backup instructions.
6. Test report and known-limitations list.
