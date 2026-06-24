---
name: month-end-close
description: Run a structured month-end close process. Walks through reconciliation, accruals, journal entries, and reporting deadlines. Use at the start of each close cycle to stay on track and catch issues early.
triggers:
  - month end close
  - closing the books
  - month end checklist
  - reconciliation
  - close process
allowed-tools: []
---

# Month-End Close

## Writes
- `outputs/month-end-close-[YYYY-MM].md`

## Context Scan

Check `context/` and `reference/` for:
- Chart of accounts or GL structure
- Prior month close notes
- Known open items from last close
- Reporting deadlines

## Step 1 — Pre-Close Preparation

Before starting the close, verify:

- [ ] All transactions through the last day of the month are posted
- [ ] Bank feeds are current and matched
- [ ] All invoices for the month are entered (AR and AP)
- [ ] Payroll for the month is processed and posted
- [ ] Credit card statements are reconciled
- [ ] Intercompany transactions are matched (if applicable)

Flag anything incomplete. Each missing item is a potential delay.

## Step 2 — Account Reconciliation

Reconcile each balance sheet account category:

### Cash and Bank Accounts
| Account | GL Balance | Bank/Statement Balance | Difference | Status |
|---------|-----------|----------------------|-----------|--------|
| [Account] | | | | Reconciled / Open |

For each difference: identify the item (timing, error, or missing entry) and the resolution.

### Accounts Receivable
- Total AR balance vs. aging report
- Items over 90 days: review for write-off or escalation
- Credit balances: investigate and clear

### Accounts Payable
- Total AP balance vs. vendor statements
- Unmatched purchase orders
- Duplicate payment check

### Prepaid Expenses and Accruals
- Amortize prepaid expenses (insurance, software, rent)
- Accrue expenses incurred but not yet invoiced
- Reverse prior month accruals that have now been invoiced

### Fixed Assets
- New additions this month
- Depreciation entries posted
- Disposals recorded

## Step 3 — Journal Entries

List all manual journal entries needed for this close:

| # | Description | Debit Account | Credit Account | Amount | Recurring? |
|---|------------|--------------|---------------|--------|-----------|
| 1 | [Entry description] | | | | Y/N |

For each entry: include the business reason. "Because we always do this" is not a reason. If you cannot explain why the entry exists, flag it for review.

## Step 4 — Revenue Recognition

- Confirm revenue recognized matches delivery/performance obligations
- Deferred revenue roll-forward: opening balance + new billings - recognized = closing balance
- Flag any revenue that needs management judgment or estimate

## Step 5 — Variance Analysis

Compare actuals to budget for major line items:

| Line Item | Actual | Budget | Variance | Variance % | Explanation |
|-----------|--------|--------|----------|-----------|-------------|
| [Item] | | | | | |

Flag any variance over 10% or over a dollar threshold relevant to the business. Every material variance needs a one-line explanation.

## Step 6 — Close Checklist Sign-Off

| Task | Owner | Status | Notes |
|------|-------|--------|-------|
| Bank reconciliation | | | |
| AR reconciliation | | | |
| AP reconciliation | | | |
| Accruals posted | | | |
| Depreciation posted | | | |
| Revenue recognized | | | |
| Journal entries reviewed | | | |
| Trial balance reviewed | | | |
| Variance analysis complete | | | |
| Financial statements drafted | | | |

## Step 7 — Open Items for Next Month

List anything that could not be resolved this close and must carry forward:

| Item | Why Unresolved | Impact | Target Resolution |
|------|---------------|--------|------------------|
| [Item] | | | |

## Do NOT
- Skip reconciliation for "small" accounts. Small accounts hide errors that compound.
- Post journal entries without descriptions. Future you (or your auditor) will need to understand why.
- Close the books with unreconciled differences. Investigate first, even if it delays the close by a day.
- Forget to reverse one-time accruals from the prior month. Double-counted accruals are a common close error.
