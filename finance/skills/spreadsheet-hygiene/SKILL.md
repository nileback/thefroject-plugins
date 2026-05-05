---
name: spreadsheet-hygiene
description: Audit and clean spreadsheets. Find broken formulas, standardize formats, detect data quality issues, document assumptions. For model-specific audits (financial models with assumptions and outputs) this is the right starting skill. Pairs with xlsx-handler for the file operations.
triggers:
  - spreadsheet audit
  - clean spreadsheet
  - broken formulas
  - data quality
  - model audit
  - excel cleanup
---

# Spreadsheet Hygiene

Audit a spreadsheet (or set of spreadsheets) for hygiene issues. Output a clean version plus a list of findings the user should review before trusting the data downstream.

## Gather context

Ask if not provided:

1. **What's the file?** — path or paste. Multi-sheet workbook?
2. **What's it used for?** — financial model, customer list, KPI dashboard, ad-hoc analysis?
3. **Confidence level needed?** — quick directional check vs. audit-grade rigor (board report, fundraise model)?
4. **Source of truth?** — is this the canonical version or a copy of one? Where does the data come from?

## The audit checklist

### Structural
- **One sheet, one purpose.** A "data" sheet, a "calc" sheet, an "output" sheet. Mixing inputs and outputs creates fragility.
- **Color-code inputs and outputs.** Convention: blue = hard-coded input, black = formula, green = link from another sheet. Spot violations.
- **Named ranges** for important inputs. Easier to read formulas referencing `tax_rate` than `Sheet2!$B$15`.
- **No hidden rows/columns** carrying logic. Hidden = forgotten = future bug.
- **No merged cells in data ranges.** Merging breaks sorting, filtering, and most formulas.

### Formulas
- **No hard-coded numbers inside formulas.** `=A1*1.07` is wrong; the 1.07 should be a named cell.
- **Consistent formula across rows.** If row 5 uses one formula and row 6 uses a different one, that's a bug-in-waiting. Fill or paste-special.
- **#REF!, #DIV/0!, #N/A, #VALUE!** errors. Each one is a logical break. Don't suppress with IFERROR until you understand why it failed.
- **Circular references** (unless intentional with iteration enabled). Flag and explain.
- **External links** to other workbooks. They break when files move; document them or eliminate.

### Data quality
- **Duplicates** — based on what key? Show samples before deleting.
- **Trailing whitespace** in text cells. Standardize.
- **Date formats inconsistent** (some dates as text, some as serial). Coerce to one format.
- **Numbers stored as text** (left-aligned numerics). Coerce.
- **Empty rows/columns** in the middle of a data range. Decide: fill, delete, or document.
- **Sentinel values** (-999, "N/A", "TBD") that should be empty. Replace consistently.

### Documentation
- **Assumptions stated.** Every model has assumptions. They should be on a clearly-labeled assumptions sheet, not hidden in formulas.
- **Sources cited.** Where did the data come from? When was it pulled?
- **Author and version.** Who built this and when? Critical for audit trail.

## Workflow

1. Open with `xlsx-handler` or via Python (`openpyxl`).
2. Print structure: sheet names, dimensions per sheet, named ranges, external links.
3. Run the checklist above sheet-by-sheet.
4. Save findings to `outputs/spreadsheet-audits/<file-stem>-findings.md`.
5. If asked to clean, save the cleaned version to `outputs/spreadsheet-audits/<file-stem>-cleaned.xlsx` (don't overwrite the source).
6. Report changes made and items flagged for the user to verify.

## Findings document format

```
## Audit: <filename>
- Date: <date>
- Reviewer: <user or skill>
- Confidence level requested: <quick / audit-grade>

## Summary
- Critical issues: <count>
- Warnings: <count>
- Notes: <count>

## Critical issues (must fix before trusting)
1. <description> — sheet, cell ref, recommended fix.
2. ...

## Warnings (should fix)
1. ...

## Notes (informational)
1. ...

## What I changed (if cleaning was done)
- ...

## What I did NOT change (flagged for user review)
- ...
```

## Common mistakes

- Auto-fixing things you don't fully understand. Some "errors" are intentional.
- Removing duplicates without confirming the dedup key.
- Standardizing dates without confirming the format the user wants.
- Cleaning the source file instead of saving a copy.
- Not stating what you didn't fix. The user should know what to verify.

## Cross-references

For the file I/O itself, use `xlsx-handler`. For financial models specifically, see `financial-model-builder`. For audit-prep workflows, use `audit-prep-guide`. For finance-side data quality monitoring as an ongoing program, set up a kaizen cadence with `kaizen-improvement`.
