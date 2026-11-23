---
name: china-expense-ledger
description: Audit and maintain a China-based company's multi-currency expense ledger and mirrored receipt files.
---

# China Expense Ledger: Maintenance

Keep the ledger row, original receipt PDF and cloud link consistent for each expense. Follow the owner's current instructions and inspect the live ledger before relying on a template or historical row numbers.

## Audit and approval

Read the full sheet: headers, data rows, monthly subtotals, spacers, totals, formulas, text and links. Match receipts by invoice or order ID; matching dates and amounts alone do not prove duplicates. Propose specific changes, with old and new values, and obtain approval before ledger writes unless the owner has already approved the specific work.

Never invent a date, amount, rate, payment method or invoice number. Leave unknowns blank and flag them. Open each original PDF and match the vendor, invoice ID, date and amount before linking. A working URL alone does not establish that a receipt matches. Keep invoice IDs as text; verify digits against source documents before converting existing numeric cells.

## Currency and totals

- Record the currency and amount actually charged. Retain any different invoice face currency as supporting detail, without counting the transaction twice.
- Convert foreign-currency expenses to RMB at the invoice-date daily mid-rate; for a weekend use the previous business day. Record the source, currency pair, effective date and retrieval date. If the rate cannot be verified, leave it blank and explicitly flag any totals that exclude the expense.
- Show original-currency totals separately by currency; never add unlike units. Check each currency's converted RMB total and the grand total.
- Use currency-aware formats: for example, USD $, HKD HK$, RMB ¥. Do not apply a universal dollar symbol.
- Record genuinely paid charges. Do not add cancelled items, free orders or credit notes as new spending; investigate refunds and reconcile them against the original payment.

## Structure and formatting

Inspect the live sheet first. Its historical arrangement uses A Date, B Vendor, C Description, D Category, E Currency, F Amount, G exchange rate, H RMB, I Payment Method, J Invoice/Receipt No., K legacy link, L receipt link and M Remark. Column names, positions and totals may change; verify them before editing. Ask before restructuring unless expressly authorized.

Insert rows bottom-up. Recheck monthly subtotal ranges, grand-total formulas and links when rows move. Verify that label-based subtotal formulas cover the intended rows and count each subtotal once. Apply values, formulas, totals and formatting in dependency order, then read back and verify the saved results.

Use consistent fonts, real dates and readable formatting. Headers and subtotal bars may be bold; retain meaningful fills and borders. Align amounts right and text left and wrap as needed. Remarks record FX basis, source and unresolved issues. Some spreadsheet APIs reset omitted style properties; verify behavior and pass a complete format specification when necessary. Do not assume this applies to every tool.

## Receipt filing and backup

Use the original receipt or invoice PDF, not a reconstructed receipt. When only a confirmation or screenshot exists, identify it accurately as supporting evidence and flag the missing original.

Mirror receipt files locally and in cloud storage under `receipts/YYYY-MM/<Vendor>/`; use the existing naming convention, generally `YYYY-MM-DD_Vendor_AmountCurrency.pdf`, with invoice ID or a suffix where necessary to distinguish same-day transactions. Respect existing folder and file names. Link the matching cloud PDF in the ledger; confirm that the link actually opens the right file. Do not upload duplicates, permanently delete files or silently replace reviewed historical entries.

After authorized changes, export and verify an updated dated Excel backup in the owner's designated expense folder. Report any export or access blocker.

## Close-out

Report briefly what changed, what was verified and what remains open, including missing receipts, payment methods, rates, invoice IDs, mismatched buyer details or incomplete backups. Source: owner's expense workflow and supplied Tencent AI summary, 2026-11-23.
