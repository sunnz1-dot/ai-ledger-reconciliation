# AI-Assisted Ledger Reconciliation

An auditable workflow for reconciling two companies' Excel ledgers, separating timing differences from genuine accounting variances, and producing a formula-driven exception report.

> This repository contains synthetic demonstration data only. Company names, transaction details, contacts, and commercially sensitive information have been removed.

## Why I built it

Manual reconciliation often fails for reasons that simple lookups cannot resolve: the two ledgers may cover different cut-off dates, one side may post prior-period transactions in the current month, and discounts or weight adjustments may be embedded in one workbook but recorded separately in the other.

I designed this reusable ChatGPT Skill to turn that ambiguous process into a structured and reviewable workflow.

## What the workflow does

1. Inspects both workbooks and identifies their reliable date coverage, amount fields, opening balances, payments, and ending balances.
2. Establishes the overlapping comparison period before matching records.
3. Normalises gross amounts, actual settlement amounts, discounts, refunds, fees, and weight adjustments.
4. Matches records by document reference, exact amount, date, and business description.
5. Separates opening carryover, cross-period corrections, and current-period variances.
6. Explains every non-zero difference with the underlying arithmetic and recommended follow-up.
7. Produces a formula-driven Excel report with management detail, disaggregated audit detail, and consistency checks.
8. Reconciles the result independently through transaction totals, a period bridge, and same-cut-off ending balances.

## Demonstration logic

The workflow is designed to distinguish common exception types such as missing ancillary charges, prior-period orders posted late, rounded adjustments versus exact calculations, and aggregate deductions that may duplicate document-level adjustments. Timing pairs are netted across the full comparable period, while genuine pricing and settlement differences remain in the cumulative result.

## Repository structure

```text
.
├── README.md
├── README_CN.md
├── skill/
│   └── SKILL.md
└── docs/
    └── methodology.md
```

## Design decisions

- Comparable dates are established before matching, so later unmatched transactions are treated as non-comparable items rather than false exceptions.
- Actual settlement amounts are preferred when the workbook explicitly calculates discounts or weight adjustments.
- Full source precision is retained during analysis; rounding is applied only to the final currency presentation.
- Management summaries may group related items, but the audit layer preserves separate documents, causes, and corrective actions.
- Every subtotal, cumulative difference, and consistency check is formula-driven in the final Excel deliverable.

## My contribution

I designed the reconciliation logic, matching hierarchy, cross-period bridge, variance taxonomy, explanation standard, and Excel output specification. I also tested the workflow against a real two-party reconciliation case before replacing all source data in this repository with synthetic examples.

## Skills demonstrated

`AI workflow design` · `Excel analysis` · `financial controls` · `data normalisation` · `exception analysis` · `requirements design` · `auditability`

## CV-ready description

> Designed a reusable AI-assisted Excel reconciliation workflow that identifies comparable periods, matches bilateral ledger records, isolates timing and settlement variances, explains each exception, and produces a formula-driven audit report with three-way consistency checks.
