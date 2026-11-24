# FUTURE™ Expense Workflow Log

## 2026-11-23 — Monthly expense review delegated to Gemini

Effective 2026-11-23, Gemini is the sole recurring runner for FUTURE™ / 上海炜禾文化传播有限公司 expense scanning, multi-inbox reconciliation, receipt filing, FX conversion checks and dated Excel proposal preparation. ChatGPT, Codex and Tencent Docs AI should use Gemini’s saved reports and proposals. The former ChatGPT check (originally biweekly, later monthly) stays disabled. Do not run duplicate recurring scans. Live Tencent Docs edits require Bill’s explicit approval.

Gemini’s monthly task, **Review FUTURE monthly expenses**, runs on the 1st around 11:00 a.m. America/Los_Angeles. In Asia/Shanghai this is the 2nd at 03:00 during Pacific standard time and 02:00 during Pacific daylight time.

Each run searches all four authorized Gmail accounts from seven days before the last successful review through the current run and reconciles against the latest Tencent Excel export in the synced `EXPENSE_dl/` folder. Mirror new original PDFs under `EXPENSE_dl/receipts/YYYY-MM/<Vendor>/`, save a dated proposed `.xlsx` in `EXPENSE_dl/` when verified changes need review, and email the summary to the designated FUTURE business inbox.

The private Notion expense guide and local expense guide hold the mailbox list, report address and full folder path. Use the existing [ledger maintenance skill](./SKILL.md) for reconciliation and workbook rules.
