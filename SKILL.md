---
name: china-expense-ledger
description: Keep a small China-based company's expense ledger, receipt files and receipt links consistent so a bookkeeper can reconcile them. Use when adding expense rows, naming/filing receipts, or auditing the ledger.
---

# China Expense Ledger: Format and Naming

## Why this exists

A small company operating in the Chinese market has to hand its expenses to a local bookkeeper or finance manager. That person needs three things to agree for every expense: a **ledger row**, a **receipt file**, and a **link** from the row to the file. Expenses come from many vendors, in USD and RMB, paid by different methods. If rows, filenames and links drift apart, reconciliation becomes slow and error-prone.

This skill defines one fixed format so any person or AI produces the same result every time.

## Rules for the AI

1. Follow this format exactly. Do not invent columns, folders or naming schemes. Ask before changing anything.
2. Never guess missing information (amount, date, payment method, invoice number). Leave it empty and ask.
3. Never permanently delete. Move replaced files to a trash or `_replaced/` folder.
4. Do not edit historical entries that the finance manager has already reviewed. Apply the format to new entries.
5. Use only the real receipt or invoice. Never use a screenshot, cart page, confirmation email or AI-rebuilt document as the receipt. If only a stand-in exists, say so and ask for the real one.

## The three matching pieces

| Piece | Description |
|---|---|
| Ledger row | One row per expense in the shared spreadsheet |
| Receipt file | PDF stored in `receipts/YYYY-MM/<Vendor>/` |
| Receipt link | Spreadsheet cell linking to the same file in cloud storage |

All three must agree on date, vendor, amount and invoice number.

## Ledger columns

| Col | Name | Notes |
|---|---|---|
| A | Date | Date on the invoice or receipt |
| B | Vendor | Vendor name |
| C | Description | What was bought |
| D | Category | Company expense category |
| E | Currency | `USD` or `RMB` |
| F | Original Amount | Amount as charged |
| G | FX Rate (USD/CNY) | USD rows only; market close on the charge date (previous business day for weekends) |
| H | Amount (RMB) | USD rows: `F x G`. RMB rows: `F` |
| I | Payment Method | Card, wallet or `Company invoice`. Add ` (reimbursable)` tag if applicable. Empty if unknown |
| J | Invoice/Receipt No. | Exactly as printed; store as text |
| K | Legacy link | Not used for new rows |
| L | Receipt link | `=HYPERLINK("<file URL>","<filename>")` |
| M | Remark | Only for refunds or notes that affect an existing charge |

- One subtotal row per month: `SUM` of that month's column H. Never write into subtotal rows.
- No duplicate invoice numbers.
- Credit notes, cancelled items and fully refunded charges do **not** get a row.

## File naming

```
YYYY-MM-DD_Vendor_AmountCurrency.pdf
```

Examples: `2026-10-11_VendorA_45.00USD.pdf`, `2026-08-17_VendorB_640.00RMB.pdf`.

- Some vendors also append the invoice or order number:
  `2026-09-27_VendorC_14.99USD_30938692.pdf`.
- Same vendor, same day, same amount: add `_a`, `_b`, `_c`.
- The link text in column L equals the filename.
- Renaming or moving a cloud file keeps its URL; update the link text after renaming.

## Folder layout

```
receipts/
  YYYY-MM/
    VendorName/
      YYYY-MM-DD_VendorName_AmountCurrency.pdf
```

Mirror this layout in local storage and in cloud storage.

## Filing a new expense

1. Get the real invoice or receipt (PDF).
2. Rename it to the standard.
3. Put it in `receipts/YYYY-MM/<Vendor>/` locally.
4. Upload the same file to the mirrored cloud folder and copy its URL.
5. Add the ledger row (columns A to J), then the link in L.
6. Check the row against the audit list.

## Replacing a file

Move the old file to trash first, upload the new one, then update the link in column L.

## Audit checklist

1. `H = F x G` on every USD row; subtotals and grand total correct.
2. Every row has an invoice number and a working receipt link.
3. Link text equals the filename.
4. Date and amount match the receipt; FX rate matches the charge date.
5. Local file, cloud file and ledger row agree.
6. The receipt is a real document, not a screenshot or rebuild.
7. Invoice buyer name and tax ID match the company, where an invoice is issued to the company.

Report findings as a short plain list, most important first. Fix only what the owner approves, except mistakes you made yourself.
